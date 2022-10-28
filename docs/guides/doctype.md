# html5の`doctype`を使用する

html5の`doctype`([Document Type Definition - DTD](https://developer.mozilla.org/en-US/docs/Glossary/Doctype))が`html`ページに指定されていることを確認してください:

```html
<!DOCTYPE html>
```

`doctype`はブラウザのレイアウトや計測用apiに影響を与えます。`doctype`を指定しないのは苦痛の世界です🔥。ブラウザは、レイアウトや計測方法を大幅に変更できる["Quirks mode"](https://en.wikipedia.org/wiki/Quirks_mode)など、他の`doctype`を使用します([more information](https://www.w3.org/QA/Tips/Doctype))。html5の`doctype`は、私たちがサポートする唯一の`doctype`です。

`production`ビルドでない場合、html5の`doctype`が見つからないと`console`に警告が記録されます。お好みで[警告を無効にする](#disable-warnings)ことができます。

[←ドキュメントに戻る](/README.md#documentation-)
