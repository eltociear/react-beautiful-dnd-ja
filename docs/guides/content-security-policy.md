# コンテンツセキュリティポリシー

> このページは、CSPエラーを回避するためのものです: "Refused to apply inline style because it violates the following Content Security Policy directive: "style-src 'self'"."
> この取り組みを推進した[@Zweder](https://github.com/Zweder)に多大な感謝を捧げます

CSP（Content Security Policy）とは、ブラウザがどこからアセットのダウンロードを許可するか、また、それらのアセットの実行を許可するかを制御する方法である。

CSPの背景を読む

- [Google guide](https://developer.chrome.com/extensions/contentSecurityPolicy)
- [MDN](https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP)
- [Helmetjs guide](https://helmetjs.github.io/docs/csp/)

`react-beautiful-dnd`は`<head>`内に`<style>`要素を作成し、その値を動的に更新します([/docs/guides/preset-styles.md]および[Dragging React performance forward](https://medium.com/@alexandereardon/dragging-react-performance-forward-688b30d40a33)を参照)。これは _unsafe inline_ と見なされ、厳格なCSPポリシーに違反することになります。Content-Security-Policy: style-src 'self'`に違反します

## オプション1: `unsafe-inline`を使用する

単純な解決策その1、より緩い`style-src 'unsafe-inline'`を使用する。⚠️これはCSPを緩めることになるので、理想的ではありません。

```diff
- Content-Security-Policy: style-src 'self'
+ Content-Security-Policy: style-src 'unsafe-inline'
```

## オプション2: `nonce`を使用する

より厳格なディレクティブである`Content-Security-Policy: style-src 'self'`は、`nonce`(一度だけ使用する番号)を指定すれば使用することができます。

[JSS](https://cssinjs.org/?v=v10.0.0)プロジェクトには素晴らしい[CSPガイド](https://cssinjs.org/csp)があり、`nonce`をどのように設定すればよいかが説明されています。ブラウザで`nonce`の値を取得したら、それを`<DragDropContext />`に渡して、`react-beautiful-dnd`に`nonce`を使用するように伝えることができます。

```js
<DragDropContext nonce={getNonce()}>{/*...*/}</DragDropContext>
```

[←ドキュメントに戻る](/README.md#documentation-)
