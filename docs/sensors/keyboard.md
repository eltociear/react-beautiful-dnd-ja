# キーボードドラッグ

`react-beautiful-dnd` は、キーボードのみでのドラッグをサポートしています。私たちは、私たちのキーボードショートカットが標準的なブラウザのキーボード操作とどのように相互作用するかを監査しました。ドラッグしていないときは、ユーザーは通常通りキーボードを使うことができます。ドラッグしているときは、ブラウザの特定のショートカット(例えば `tab`)を無効にして、ユーザがスムーズに操作できるようにします。

> 標準的なブラウザのイベントにどのように影響を与えるかについてのより詳細な情報は、[DOM イベントガイドの使用方法](/docs/guides/how-we-use-dom-events.md)をご覧ください。

## キーボードショートカット: キーボードドラッグ

ドラッグが発生していない場合、ユーザーは標準の **tab**<kbd>tab ↹</kbd> キーを使用してページ上の `<Draggable />` をナビゲートし、次のページに移動できます。タブ可能な要素と (**shift** + **tab**) (<kbd>shift</kbd> + <kbd>tab ↹</kbd>) で後方に移動します。これは、`<Draggable />` に `tab-index` を追加することで実現します。`<Draggable />` にフォーカスがあるとき、**spacebar**<kbd>space</kbd> は `<Draggable />` を**持ち上げ**ます。これにより、ドラッグが開始されます。

ドラッグを開始すると、以下のキーボードショートカットが使用できます:

- **spacebar** <kbd>space</kbd> - `<Draggable />` をドロップ
- **escape** <kbd>esc</kbd> - ドラッグをキャンセル

以下のコマンドも利用できますが、これらは `<Draggable />` が現在属している `<Droppable />` の `type` に依存します:

### 垂直方向のリスト内

- **Up arrow** <kbd>↑</kbd> - `<Draggable />` を `<Droppable />` の上方向に移動
- **Down arrow** <kbd>↓</kbd> - `<Draggable />` を `<Droppable />` の下方向に移動
- **Right arrow** <kbd>→</kbd> - `<Draggable />` を、現在の `<Droppable />` の _右_ 側に移動(新しいリストへ移動)
- **Left arrow** <kbd>←</kbd> - `<Draggable />` を、現在の `<Droppable />` の _左_ 側に移動(新しいリストへ移動)

### 水平方向のリスト内

- **Up arrow** <kbd>↑</kbd> - `<Draggable />` を、現在の `<Droppable />` の _上_ に移動(新しいリストへ移動)
- **Down arrow** <kbd>↓</kbd> - `<Draggable />` を、現在の `<Droppable />` の _下_ に移動(新しいリストへ移動)
- **Right arrow** <kbd>→</kbd> - 現在の `<Droppable />` 内の `<Draggable />` を _右_ へ移動
- **Left arrow** <kbd>←</kbd> - 現在の `<Droppable />` 内の `<Draggable />` を _左_ に移動

ドラッグ中は、以下の標準的なキーボードイベントのデフォルトの動作が阻止されます(`event.preventDefault()` を使用します):

- **tab** <kbd>tab ↹</kbd> - タブ化防止
- **enter** <kbd>⏎</kbd> - 送信防止

## 自動スクロール

キーボードでドラッグすると、`react-beautiful-dnd` は[自動スクロール](/docs/guides/auto-scrolling.md)操作を行い、アイテムを移動できるようにします

[auto-scroll-board-keyboard](https://user-images.githubusercontent.com/2182637/36520650-3d3638f8-17e6-11e8-9cba-1fb439070285.gif)

[←ドキュメントに戻る](/README.md#documentation-)
