# テーブル

| `<table>`を使用するメリット              | 提供者                    |
| ------------------------------------- | ------------------------ |
| 表形式データのクリーンな表示方法           | ブラウザー                 |
| 優れたブラウザサポート                   | ブラウザー                 |
| 他のアプリケーションに表をコピーペースト可能 | ブラウザー                 |
| テーブルの中の項目を並び替え可能！         | `react-beautiful-dnd` 😎 |

`react-beautiful-dnd`では、`<Draggable />`と`<Droppable />`コンポーネントを作成するために、追加のラッピング要素を必要としません。そのため、ドラッグ＆ドロップをサポートするだけでなく、有効なHTMLを持つ`<table>`を作成することができます。

> 現段階では、テーブルのカラムを意味的に並べ替える方法は見つかっていません。これは、テーブルの列を表す要素は一つもないからです。むしろ、列は繰り返される行の中のセルの配置の結果なのです。そのため、`<Draggable />`を'column'に巻いて、それをドラッグできるようにすることはできません。うまくいく方法を見つけたら、このガイドの PR をお願いします!

## ストラテジー

テーブルの並び替えには2つの方法があります。

1.  レイアウトの固定化（高速化、簡素化）
2.  ディメンションロック（低速だがより堅牢）

### 戦略1: レイアウトの固定化

この方法を使うには、カラムの幅を固定する必要があります。つまり、セル内に配置されるコンテンツによって幅が変わることはありません。これは`table-layout: fixed`や`table-layout: auto`で実現することができますが、セルの幅を手動で設定する必要があります(例:`50%`)。

必要なことは、ドラッグ中の`<Draggable />`行に`display: table`を設定することだけです。

[サンプルコードはこちら](https://react-beautiful-dnd.netlify.com/?selectedKind=Tables&selectedStory=with%20fixed%20width%20columns&full=0&addons=1&stories=1&panelRight=0&addonPanel=storybook%2Factions%2Factions-panel)

一部のユーザーは `table-layout` と `display: table` のアプローチを使用して問題を経験したことがあります。具体的には、固定レイアウトのそのアプローチは、一度要素がドラッグされるとスタイリングを維持しません。代替案としては、`<Draggable />` がドラッグされたときに `table-layout` や `display: table` を設定せず、各 `<td>` の `width` を永続的に設定することです。これにより、イベントレスポンダを使用する必要がなくなります。例えば、`<Draggable />` の中で、インラインスタイルか css で各 `<td>` に `width: 100px` をセットします。この方法は、[コードサンドボックスはこちら](https://codesandbox.io/s/vertical-list-s9rx5?fontsize=14&hidenavigation=1&theme=dark)で見ることができます。

### 戦略2: ディメンションロック

この方法は、コンテンツに応じて列の幅が自動的に調整されるような列で有効です。また、固定レイアウトでも動作します。 **1つ目の方法よりも強固な方法ですが、性能は落ちます。**

ドラッグするアイテムに`position: fixed`を適用すると、テーブルが使用する自動列幅計算の対象から外れることになります。そこで、ドラッグを開始する前に、インラインスタイルを使用してすべてのセル幅を _ロック_ し、ドラッグ開始時に列の寸法が変更されないようにします。これは[`onBeforeDragStart`レスポンダ](/docs/guides/responders.md)を使って実現できます。

これは、必要に応じて大規模なパフォーマンス特性が低下します:

1.  各行で`render()`を呼び出す
2.  各行でDOM(`window.getComputedStyles`)を読み取る

50行以下のテーブルの場合、この方法で問題ありません!

[サンプルコードはこちら](https://react-beautiful-dnd.netlify.com/?selectedKind=Tables&selectedStory=with%20dimension%20locking&full=0&addons=1&stories=1&panelRight=0&addonPanel=storybook%2Factions%2Factions-panel)

## 高度: リペアレント

もしリペアレント（クローンまたは独自のポータル）をテーブルの行の並べ替えと組み合わせて使用したい場合は、いくつかの追加手順を踏む必要があります。

まず最初に、私たちの[reparenting pattern](/docs/guides/reparenting.md)を読んで、アプローチに慣れてください。

Reactでマウント/アンマウントのアクションのタイミングを知ることは重要です。`ReactDOM.createPortal`に出入りする際のマウントのタイミングを示す[codesandbox.io example](https://codesandbox.io/s/nkl52y1wn0)を作成しましたのでご覧ください。

既存の`<tr>`を`ReactDOM.createPortal`に移動する場合、既存の`<tr>`がアンマウントされ、新しい`<tr>`がポータルにマウントされることを知っておくことが重要です。以下はその操作の順序です:

1.  `componentWillUnmount`がコールされると古い`<tr>`
2.  `componentWillMount`がコールされると新しい`<tr>`

`ReactDOM.createPortal`に移動する行のセルの寸法を保持するために、インラインスタイルを使用して寸法を固定する必要があります（戦略2を参照）。しかし、悲しいことに、新しいコンポーネントは、ポータルに移動する前にツリーにあったコンポーネントの情報に直接アクセスすることができません。そのため、アンマウント時に`<tr>`のセル寸法を取得し、`componentDidMount`でマウント時に新しい`<tr>`に再適用する必要があります。

というのも、`componentDidMount`が呼ばれたとき、`<tr>`が不要になったからアンマウントしているのか、それともポータルに移動しようとしてアンマウントしているのかが分からないからです。

物事を機能させる唯一の方法は:

1.  `<tr>`の`componentWillUnmount`で、DOMからセルの現在の幅を読み取ります。そして、この値をコンポーネントの外側に保存して、新しくマウントされるコンポーネントから読み取れるようにします。
2.  コンポーネントがマウントされていて、`DraggableStateSnapshot > isDragging`がtrueの場合、以前に記録された幅があるかどうかを確認することができます。もしあれば、その幅を適用することができる。

これは少し複雑なので、このテクニックがどのように機能するかを示すために、いくつかの例を作成しました:

- [クローン作成APIを使用する場合](https://react-beautiful-dnd.netlify.com/?path=/story/tables--with-clone)
- [独自のポータルサイトを使用する場合](https://react-beautiful-dnd.netlify.com/?path=/story/tables--with-portal)

どういたしまして！

[←ドキュメントに戻る](/README.md#documentation-)
