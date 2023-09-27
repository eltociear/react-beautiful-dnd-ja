# エンジニアリングヘルス

[![CircleCI branch](https://img.shields.io/circleci/project/github/atlassian/react-beautiful-dnd/master.svg)](https://circleci.com/gh/atlassian/react-beautiful-dnd/tree/master)

## タイプ

[![Typed with flow](https://img.shields.io/badge/typed%20with-flow-brightgreen.svg?style=flat)](https://flow.org/)

このコードベースは [flow](https://flow.org) で型付けされており、内部一貫性を高め、より弾力的なコードを実現しています。

`TypeScript` と `flow` のサポートについては、[タイプガイド](/docs/guides/types.md)で詳しく説明されています。

## テスト済

[![Tested with jest](https://img.shields.io/badge/tested_with-jest-99424f.svg)](https://www.npmjs.com/package/react-beautiful-dnd) [![Tested with cypress](https://img.shields.io/badge/tested%20with-cypress-brightgreen.svg?style=flat)](https://www.cypress.io/)

このコードベースでは、ユニットテスト、統合テスト、ブラウザテスト、パフォーマンステストなど、さまざまなテスト戦略を採用しています。システムの様々な側面をテストすることで、その品質と安定性を促進することができます。

コードカバレッジは[コードの健全性を保証するものではありません](https://stackoverflow.com/a/90021/1374236)が、良い指標にはなります。このコードベースは現在 **~94% のカバレッジ** にとどまっています。

## リント

- [`eslint`](https://eslint.org/)
- [`stylelint`](https://github.com/stylelint/stylelint)
- [`prettier`](https://github.com/prettier/prettier) - まあ、厳密にはリンターではないのですが、近いものがあります。

## パフォーマンス

[![CircleCI branch](https://img.shields.io/badge/speed-blazing%20%F0%9F%94%A5-brightgreen.svg?style=flat)](https://circleci.com/gh/atlassian/react-beautiful-dnd/tree/master)

このコードベースは、**極めて高いパフォーマンスを発揮するよう** に設計されています - これは DNA の一部です。可能な限り最小限の更新を行うように設計されています。`react-beautiful-dnd` のために行われたパフォーマンスに関する研究は、こちらで読むことができます:

- [Rethinking drag and drop](https://medium.com/@alexandereardon/rethinking-drag-and-drop-d9f5770b4e6b)
- [Dragging React performance forward](https://medium.com/@alexandereardon/dragging-react-performance-forward-688b30d40a33)
- [Grabbing the flame 🔥](https://medium.com/@alexandereardon/grabbing-the-flame-290c794fe852)

> [メディア](/docs/support/media.md)に詳細があります。

## サイズ

[![minzip](https://img.shields.io/bundlephobia/minzip/react-beautiful-dnd.svg)](https://www.npmjs.com/package/react-beautiful-dnd)

このライブラリは、可能な限り軽量になるように細心の注意が払われています。もし、既に依存関係にあるライブラリを使用している場合は、より小さなコストで済むかもしれません。

[←ドキュメントに戻る](/README.md#documentation-)
