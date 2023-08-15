# `resetServerContext`

`resetServerContext` 関数は、サーバーサイドレンダリング(SSR) の際に使用します。これは、サーバ上で複数のレンダリングを行う際にコンテキストの状態が持続しないようにするもので、サーバ上で複数のリクエストをレンダリングした後にクライアント/サーバのマークアップの不一致が発生することになる。

サーバーサイドレンダリングメソッドを呼び出す前に使用する:

```js
import { resetServerContext } from 'react-beautiful-dnd';
import { renderToString } from 'react-dom/server';

// ...

resetServerContext();
renderToString(...);
```

[←ドキュメントに戻る](/README.md#documentation-)
