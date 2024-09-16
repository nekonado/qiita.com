---
title: JavaScriptのprintデバッグでは{variable}形式が便利
tags:
  - JavaScript
  - TypeScript
  - tips
private: false
updated_at: "2024-09-17T07:21:19+09:00"
id: 90bb23d9905e3f148191
organization_url_name: SasukeFL
slide: false
ignorePublish: false
---

JavaScript や TypeScript で print デバッグを行うとき、確認対象と変数名を一緒に表示するためにラベル用の文字列をつけて表示することがあるかと思います。例えば以下の感じ。

```javascript
const cat = { emoji: "🐈" };
const dog = { emoji: "🐕" };
console.log("cat: ", cat); // -> cat:  { emoji: '🐈' }
console.log("dog: ", dog); // -> dog:  { emoji: '🐕' }
```

このとき、[オブジェクトの値の省略記法](https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Operators/Object_initializer#%E3%83%97%E3%83%AD%E3%83%91%E3%83%86%E3%82%A3%E3%81%AE%E5%AE%9A%E7%BE%A9)を使うと便利です。

これは「キーと同じ名称の変数を値にとるオブジェクトを生成するときには値の記述を省略できる」というもので、確認対象の変数をオブジェクト初期化子でラップすることで結果としてラベル（キー）つきで表示できます。

```javascript
// my favorite style
console.log({ cat }); // -> { cat: { emoji: '🐈' }
console.log({ dog }); // -> { dog: { emoji: '🐕' }
```

この方法を使うと、変数名を繰り返す必要がなくなり、またエディタのリネーム機能（e.g. [VSCode の場合](https://code.visualstudio.com/docs/editor/editingevolved#_rename-symbol)）を使って変数名を変更した際にラベルも一緒に変更されるため、変数名とラベルの整合性を保ちやすくなります。

コスパの良い print デバッグの tips としておすすめなので、手癖でオブジェクト初期化子でラップしておくと良いかもしれません。
