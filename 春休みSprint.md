# Flexible FizzBuzz

*(これは[codecheck](http://app.code-check.io/openchallenges)のチャレンジです。 初めての人はまず[ドキュメンテーション](https://code-check.github.io/docs/ja)を見てね。)*

あなたは FizzBuzz を知っていますか？この問題はもともと言葉遊びのゲームだったのですが、「プログラミングの経験が少なからずあるか」を知る、手軽な問題として紹介され、プログラマーに「典型的な初級問題」として広がりました。

FizzBuzz問題では、プログラムは任意の自然数を与えられ、特定の値には特定の出力を返します。アルゴリズムは3 で割り切れる場合は "Fizz" を出力。 5 で割り切れる場合は "Buzz"、そして、3 と 5 の両方で割り切れる場合は "FizzBuzz" を出力します。また、それ以外では与えられた数値をそのまま出力します。
例えば、次はJava で書かれたシンプルな FizzBuzz の実装です。

```Java
static String fizzbuzz(int num) {
  if (num % 15 == 0) return "FizzBuzz";
  if (num % 5 == 0) return "Buzz";
  if (num % 3 == 0) return "Fizz";
  return String.valueOf(num);
}
```

この問題はプログラミング経験の有無を見るにはちょうど良い問題です。  

しかし！上記の実装例には柔軟性がありません。定数が埋め込まれていて、ちょっとした変更をする場合には手作業で定数を書き換える必要があります。

## ザ・ミッション
あなたのミッションは FizzBuzz をもっと柔軟なものにすることです。  
パラメータを受け取ることで出力をカスタマイズできるCLIアプリケーションを作成してください。

## 実装方法

#### CLI
入力値を引数に取り、結果を標準出力に出力するCLIアプリケーションとして解答を実装してください。
CLIの実装方法については[指定言語].mdを参照ください。

#### 入力ルール
- 引数の数は可変する
- 引数として`:`で区切られた数値と文字列のペアを受け取る(最後の引数を除く)
- 最後に受け取る引数は文字列に変換する対象の数値とする
- 受け取った引数の数値が整数ではない場合は、`invalid input`を表示する

#### 出力ルール
- 文字列に変換する対象の数値が、与えられた数値と文字列のペアのいずれかで割り切れる場合、対応する文字列を表示する
- 複数の数値で割り切れる場合は小さい方から順番に対応する文字列を連結して表示する
- 割り切れない場合は数値をそのまま表示する

#### 入出力例

```shell
$ ./fizzbuzz 3:fizz 5:buzz hello
invalid input
$ ./fizzbuzz 3.21:fizz 5:buzz 15
invalid input
$ ./fizzbuzz 3:fizz 5:buzz 1
1
$ ./fizzbuzz 3:hoge 5:fuga 3
hoge
$ ./fizzbuzz 3:piyo 5:hogera 5
hogera
$ ./fizzbuzz 3:kabe 5:don 15
kabedon
```

また、テストケースは[testcase.json](test/testcase.json)に定義されています。

## answer.md
[answer.md](./answer.md)を用意してあるので、その中に
- どのように実装したか、工夫した点は何か
- 発生した問題、難しかった箇所
- それをどのようにして対処したのか

等を書いてください。
