<p align="center">
  <img src="https://user-images.githubusercontent.com/2182637/53611918-54c1ff80-3c24-11e9-9917-66ac3cef513d.png" alt="react beautiful dnd logo" />
</p>
<h1 align="center">react-beautiful-dnd <small><sup>(rbd)</sup></small></h1>

<div align="center">

[`React`](https://facebook.github.io/react/) を使用した**美しく**て**誰でも使いやすい**ドラッグ・アンド・ドロップリスト

[![CircleCI branch](https://img.shields.io/circleci/project/github/atlassian/react-beautiful-dnd/master.svg)](https://circleci.com/gh/atlassian/react-beautiful-dnd/tree/master)
[![npm](https://img.shields.io/npm/v/react-beautiful-dnd.svg)](https://www.npmjs.com/package/react-beautiful-dnd)

![quote application example](https://user-images.githubusercontent.com/2182637/53614150-efbed780-3c2c-11e9-9204-a5d2e746faca.gif)

[必要に応じて、この例を試してください！](https://react-beautiful-dnd.netlify.com/iframe.html?selectedKind=board&selectedStory=simple)

</div>

## 主要な特徴

- 美しく、かつ アイテムが[自然に動く](/docs/about/animations.md)💐
- [誰でも使い易い](/docs/about/accessibility.md): 強力なキーボードとスクリーンリーダーのサポート♿️
- [超ハイパフォーマンス](/docs/support/media.md) 🚀
- 使い始めるのが簡単なクリーンで強力なAPI
- 標準のブラウザ操作で非常にうまく機能
- [かっちりしたスタイリング](/docs/guides/preset-styles.md)
- 追加のラッパー DOM ノードを作成する必要なし-フレックスボックスとフォーカス管理に適しています！

## 始めましょう👩‍🏫

すぐに `react-beautiful-dnd` を始められるように、[`egghead.io` 🥚上に無料のコース](https://egghead.io/courses/beautiful-and-accessible-drag-and-drop-with-react-beautiful-dnd) を用意しています。

[![course-logo](https://user-images.githubusercontent.com/2182637/43372837-8c72d3f8-93e8-11e8-9d92-a82adde7718f.png)](https://egghead.io/courses/beautiful-and-accessible-drag-and-drop-with-react-beautiful-dnd)

## 現在サポート済の機能セット✅

- 垂直リスト↕
- 水平リスト↔
- リスト間の移動(▤ ↔ ▤)
- [仮想リストのサポート👾](/docs/patterns/virtual-lists.md) - 10,000 個のアイテムを 60 fps で解除
- [アイテムを組み合わせ](/docs/guides/combining.md)
- マウス🐭、キーボード🎹♿️ そしてタッチスクリーン👉📱（モバイル、タブレット等）サポート
- [マルチドラッグのサポート](/docs/patterns/multi-drag.md)
- 信じられないほどのスクリーンリーダーのサポート♿️ - 箱から出してすぐの英語のスクリーンリーダーに素晴らしい体験を提供します📦。また、完全なカスタマイズ制御と国際化サポートを必要とする人に提供します💖
- [条件付きドラッグ](/docs/api/draggable.md#optional-props)と[条件付きドロップ](/docs/api/droppable.md#conditionally-dropping)
- 1 ページに複数の独立したリスト
- 柔軟なアイテムサイズ - ドラッグ可能なアイテムは、さまざまな高さ（垂直リスト）または幅（水平リスト）を持つことができます
- [ドラッグ中にアイテムを追加および削除](/docs/guides/changes-while-dragging.md)
- セマンティック `<table>` の並べ替えとの互換性 - [テーブルパターン](/docs/patterns/tables.md)
- [自動スクロール](/docs/guides/auto-scrolling.md) - ドラッグ中に必要に応じてコンテナとウィンドウを自動的にスクロールします（キーボードを使用している場合でも🔥）
- カスタムドラッグハンドル - アイテムの一部だけでアイテム全体をドラッグできます
- ドラッグ中にドラッグアイテムを別の要素に移動できる（クローン、ポータル） - [`<Draggable /> の親変更`](/docs/guides/reparenting.md)
- [スクリプト化されたドラッグアンドドロップ体験を作成する🎮](/docs/sensors/sensor-api.md)
- 拡張機能が[任意の input タイプ 🕹](/docs/sensors/sensor-api.md)をサポートできるようにします
- 🌲[`@atlaskit/tree`](https://atlaskit.atlassian.com/packages/confluence/tree) パッケージによるツリーのサポート
- `<Droppable />` リストは、スクロールコンテナ（スクロール可能な親なし）またはスクロールコンテナの子（スクロール可能な親なし）にすることができます。
- 独立したネストされたリスト - リストは別のリストの子になることができますが、親リストから子リストにアイテムをドラッグすることはできません
- サーバーサイドレンダリング （SSR） 互換 - [resetServerContext()](/docs/api/reset-server-context.md)を参照してください
- デフォルトでは[ネストされたインタラクティブ要素](/docs/api/draggable.md#interactive-child-elements-within-a-draggable-)とうまく連携します

## 作成の動機🤔

`react-beautiful-dnd` は、誰でも使用できるリストの美しいドラッグアンドドロップを作成するために存在します - 見ることができない人でも。プロジェクトの歴史と動機の概要については、次の外部リソースをご覧ください：

- 📖 [ドラッグアンドドロップを再考する](https://medium.com/@alexandereardon/rethinking-drag-and-drop-d9f5770b4e6b)
- 🎧 [React podcast： 高速でアクセスしやすく、美しいドラッグアンドドロップ](https://reactpodcast.simplecast.fm/17)

## すべての人のためではありません✌️

React 内でドラッグアンドドロップの相互作用を可能にするライブラリはたくさんあります。これらの中で最も注目に値するのは、驚くべき [`react-dnd`](https://github.com/react-dnd/react-dnd) です。それは[非常に一貫性のない](https://www.quirksmode.org/blog/archives/2009/09/the_html5_drag.html) html5 ドラッグアンドドロップ機能で特にうまく機能するドラッグアンドドロッププリミティブの素晴らしいセットを提供するという素晴らしい仕事をします。`react-beautiful-dnd` は、リスト用に特別に構築された高レベルの抽象化です（垂直、水平、リスト間の移動、ネストされたリストなど）。その機能のサブセット内で、`react-beautiful-dnd` は、強力で自然で美しいドラッグアンドドロップ体験を提供します。ただし、`react-dnd` が提供する幅広い機能は提供していません。したがって、ユースケースによっては、`react-beautiful-dnd` が適切でない場合があります。

## ドキュメント📖

### アバウト👋

- [インストール](/docs/about/installation.md)
- [例とサンプル](/docs/about/examples.md)
- [始めましょう](https://egghead.io/courses/beautiful-and-accessible-drag-and-drop-with-react-beautiful-dnd)
- [設計原則](/docs/about/design-principles.md)
- [アニメーション](/docs/about/animations.md)
- [アクセシビリティ](/docs/about/accessibility.md)
- [ブラウザのサポート](/docs/about/browser-support.md)

### センサー🔉

> 誰かがドラッグを開始して制御できる方法

- [マウスによるドラッグ🐭](/docs/sensors/mouse.md)
- [タッチ操作によるドラッグ👉📱](/docs/sensors/touch.md)
- [キーボードによるドラッグ🎹♿️](/docs/sensors/keyboard.md)
- [独自センサーの作成](/docs/sensors/sensor-api.md) （任意の入力タイプとスクリプト化された体験を可能にします）

### API🏋️‍

![diagram](https://user-images.githubusercontent.com/2182637/53607406-c8f3a780-3c12-11e9-979c-7f3b5bd1bfbd.gif)

- [`<DragDropContext />`](/docs/api/drag-drop-context.md) - _ドラッグアンドドロップを有効にするアプリケーションの部分をラップする_
- [`<Droppable />`](/docs/api/droppable.md) - _ドロップ可能なエリア。`<Draggable />` を含む_
- [`<Draggable />`](/docs/api/draggable.md) - _ドラッグ可能なもの_
- [`resetServerContext()`](/docs/api/reset-server-context.md) - _サーバーサイドレンダリング （SSR） のユーティリティ_

### ガイド🗺

- [`<DragDropContext />` レスポンダー](/docs/guides/responders.md) - _`onDragStart`、`onDragUpdate`、`onDragEnd` 及び `onBeforeDragStart`_
- [`<Draggable />` を組み合わせる](/docs/guides/combining.md)
- [一般的なセットアップの問題](/docs/guides/common-setup-issues.md)
- [`innerRef` の使用](/docs/guides/using-inner-ref.md)
- [問題の検出とエラー回復の設定](/docs/guides/setup-problem-detection-and-error-recovery.md)
- [`draggableId` 及び `droppableId` のルール](/docs/guides/identifiers.md)
- [ブラウザのフォーカス保持](/docs/guides/browser-focus.md)
- [ドロップアニメーションのカスタマイズまたはスキップ](/docs/guides/drop-animation.md)
- [自動スクロール](/docs/guides/auto-scrolling.md)
- [スクリーンリーダーの制御](/docs/guides/screen-reader.md)
- [html5 の `doctype` の使用](/docs/guides/doctype.md)
- [`TypeScript` 及び `flow`: 型の情報](/docs/guides/types.md)
- [`<svg>` のドラッグ](/docs/guides/dragging-svgs.md)
- [画像のちらつきを避ける](/docs/guides/avoiding-image-flickering.md)
- [目に見えないプリセットスタイル](/docs/guides/preset-styles.md)
- [スクロールコンテナを検出する方法](/docs/guides/how-we-detect-scroll-containers.md)
- [DOM イベントの使用方法](/docs/guides/how-we-use-dom-events.md) - _`react-beautiful-dnd` 上に構築する必要がある場合に便利_
- [ドラッグ中に `<Draggable />` を追加 (11.x の動作)](/docs/guides/changes-while-dragging.md) - _⚠️高度
- [コンテンツセキュリティポリシーの設定](/docs/guides/content-security-policy.md)

### パターン👷‍

- [仮想リスト👾](/docs/patterns/virtual-lists.md)
- [マルチドラッグ](/docs/patterns/multi-drag.md)
- [テーブル](/docs/patterns/tables.md)
- [`<Draggable />` の親変更](/docs/guides/reparenting.md) - _クローン API または独自ポータルの使用_

### サポート👩‍⚕️

- [エンジニアリングヘルス](/docs/support/engineering-health.md)
- [コミュニティとアドオン](/docs/support/community-and-addons.md)
- [リリースノートと変更ログ](https://github.com/atlassian/react-beautiful-dnd/releases)
- [アップグレード](/docs/support/upgrading.md)
- [ロードマップ](https://github.com/atlassian/react-beautiful-dnd/issues)
- [メディア](/docs/support/media.md)

## 他の言語で読む🌎

- [![en](https://raw.githubusercontent.com/gosquared/flags/master/flags/flags/shiny/24/United-States.png) **English（オリジナル）**](https://github.com/atlassian/react-beautiful-dnd)
- [![kr](https://raw.githubusercontent.com/gosquared/flags/master/flags/flags/shiny/24/South-Korea.png) **한글/Korean**](https://github.com/LeeHyungGeun/react-beautiful-dnd-kr)
- [![china](https://raw.githubusercontent.com/gosquared/flags/master/flags/flags/shiny/24/China.png) **中文/Chinese**](https://github.com/chinanf-boy/react-beautiful-dnd-zh)
- [![ru](https://raw.githubusercontent.com/gosquared/flags/master/flags/flags/shiny/24/Russia.png) **На русском/Russian**](https://github.com/vtereshyn/react-beautiful-dnd-ru)
- [![pt](https://raw.githubusercontent.com/gosquared/flags/master/flags/flags/shiny/24/Brazil.png) **Português/Portuguese**](https://github.com/dudestein/react-beautiful-dnd-pt)
- [![gr](https://raw.githubusercontent.com/gosquared/flags/master/flags/flags/shiny/24/Greece.png) **Ελληνικά/Greek**](https://github.com/milvard/react-beautiful-dnd-gr)
- [![ja](https://raw.githubusercontent.com/gosquared/flags/master/flags/flags/shiny/24/Japan.png) **日本語/Japanese**](https://github.com/eltociear/react-beautiful-dnd-ja)

## 作者✍️

Alex Reardon [@alexandereardon](https://twitter.com/alexandereardon)

> Alex はもはやこのプロジェクトを個人的にメンテナンスしていません。他の素晴らしいメンテナがこのプロジェクトを進めています。

## メインテナー

- [Daniel Del Core](https://twitter.com/danieldelcore)
- 多くの[@Atlassian](https://twitter.com/Atlassian)ズ！

## コラボレイター🤝

- Bogdan Chadkin [@IAmTrySound](https://twitter.com/IAmTrySound)
