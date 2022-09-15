# インストール

[![module formats: umd, cjs, and esm](https://img.shields.io/badge/module%20formats-umd%2c%20cjs%2c%20esm-green.svg?style=flat)](https://unpkg.com/react-beautiful-dnd/dist/)

## 一般

1. `react-beautiful-dnd`パッケージを追加する

```bash
# yarn
yarn add react-beautiful-dnd

# npm
npm install react-beautiful-dnd --save
```

2. パッケージを使用する

```js
import { DragDropContext } from 'react-beautiful-dnd';
```

3. 利益🕺

## `React`環境

`react-beautiful-dnd`を使用するためには、おそらく`React`環境を構築する必要があります。

- [既存のウェブサイトに React を追加する](https://ja.reactjs.org/docs/add-react-to-a-website.html) - 公式`React`ドキュメント
- [Setup a react environment with `create-react-app`](https://egghead.io/lessons/react-set-up-a-react-environment-with-create-react-app) - [無料スタートアップ講座](https://egghead.io/courses/beautiful-and-accessible-drag-and-drop-with-react-beautiful-dnd)より

## 配布バンドル

[ユニバーサルモジュール定義](https://github.com/umdjs/umd) バンドルは、`npm`上の`/dist`フォルダに公開され、消費されます。以下のファイルを公開します:

- `dist/react-beautiful-dnd.js`
- `dist/react-beautiful-dnd.min.js` (最小化バンドル)

これらのバンドルは、提供する必要がある外部要素として`react`をリストアップしています。これは、バンドルのサイズを小さくし、コンシューマが`react`を何度も読み込むことを防ぐために行われます。モジュールシステムを通して`react`を提供するか、単に`window`に`react`を表示させることができます。

UMDを使って、ブラウザ上で直接`react-beautiful-dnd`を実行することができます。

```html
<!-- peer dependency -->
<script src="https://unpkg.com/react@16.3.1/umd/react.development.js"></script>
<!-- lib (x.x.xを希望のバージョンに変更) -->
<script src="https://unpkg.com/react-beautiful-dnd@x.x.x/dist/react-beautiful-dnd.js"></script>
<!-- reactアプリのマウントに必要 -->
<script src="https://unpkg.com/react-dom@16.3.1/umd/react-dom.development.js"></script>

<script>
  const React = window.React;
  const ReactDOM = window.ReactDOM;
  const { DragDropContext, Draggable, Droppable } = window.ReactBeautifulDnd;

  function App() {
    // ...
  }

  // JSXをサポートする環境であれば、JSXを使用することができます
  ReactDOM.render(React.createElement(App), document.getElementById('app'));
</script>
```

また、このインストール方法で試せる[example codepen](https://codepen.io/alexreardon/project/editor/ZyNMPo)も用意されています。

## [`ClojureScript`](https://clojurescript.org/)

[CLJSJS](https://cljsjs.github.io/)を使って`ClojureScript`内から`react-beautiful-dnd`を利用することができます!

[←ドキュメントに戻る](/README.md#documentation-)
