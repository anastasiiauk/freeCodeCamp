---
id: 587d7b86367417b2b2512b3d
title: 有効な終了条件を使用して無限ループを防ぐ
challengeType: 1
forumTopicId: 301192
dashedName: prevent-infinite-loops-with-a-valid-terminal-condition
---

# --description--

最後のトピックは、煩わしい無限ループです。 ループは、コードブロックを特定の回数だけ、または条件が満たされるまで実行するには最適なツールですが、ループを終わらせるためには終了条件が必要です。 無限ループはブラウザーをフリーズまたはクラッシュさせ、通常のプログラムの実行を妨げる問題を引き起こす可能性があります。

このセクションの導入部に無限ループの例がありましたが、`loopy()` 内の `while` ループを抜け出すための終了条件は記述していませんでした。 次の関数を呼び出さないでください！

```js
function loopy() {
  while(true) {
    console.log("Hello, world!");
  }
}
```

プログラミングでは、終了条件、つまり、プログラムでいつループを抜け出すかを最終的に決める必要があります。 たとえば、カウンター変数を終了条件から間違った方向にインクリメントまたはデクリメントしてしまったり、 あるいはインクリメントまたはデクリメントするのではなく、ループコード内のカウンター変数やインデックス変数を誤ってリセットしてしまったりすると、エラーになります。

# --instructions--

`myFunc()` 関数には無限ループが含まれています。これは、終了条件である `i != 4` が `false` に評価される (したがって無限ループを脱する) ことが決してないからです。`i` はパスごとに 2 増えますが、`i` は奇数から始まっているため、4 はスキップされます。 `i` が 4 以下の場合にのみループが実行されるように、終了条件の比較演算子を修正してください。

# --hints--

`for` ループの終了条件 (真ん中の部分) の比較演算子を変更する必要があります。

```js
assert(__helpers.removeJSComments(code).match(/i\s*?<=\s*?4;/g).length == 1);
```

ループの終了条件にある比較演算子を修正する必要があります。

```js
assert(!__helpers.removeJSComments(code).match(/i\s*?!=\s*?4;/g));
```

# --seed--

## --seed-contents--

```js
function myFunc() {
  for (let i = 1; i != 4; i += 2) {
    console.log("Still going!");
  }
}
```

# --solutions--

```js
function myFunc() {
 for (let i = 1; i <= 4; i += 2) {
   console.log("Still going!");
 }
}
```
