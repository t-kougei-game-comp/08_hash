# ハッシュの演習

# 進め方
## はじめてのとき
* [GitHub](https://github.com/)のアカウントを作成してください
* [Travis CI](https://travis-ci.org/) のアカウントを作成してください
* GitHubのアカウントを[こちらのフォーム](https://goo.gl/forms/anAdoxqPKVt8sJGZ2)から教えてください。
## 毎回の進め方
* このリポジトリをforkしてください
* Travis CI を設定して、自動ビルドが通るようにしてください
   * Travis CI のGitHubアカウントでの登録とforkしたリポジトリをTravisCI側で許可する
   * 参考サイト：[Travis CI入門 Travis CIとGitHubでCIを実現する方法(Change the World!)](http://changesworlds.com/2014/09/introduction-to-travis-ci-and-github-001/)
* forkしたリポジトリの README.md ファイルの「t-kougei-game-comp」の部分を自分のGitHubアカウント名に差し替えてください(2箇所)
* 問題を解いて、テストを通るようにしてください。
* fork 元の master ブランチにプルリクエストを投げてください

# テスト結果

[![Build Status](https://travis-ci.org/t-kougei-game-comp/hash.svg?branch=master)](https://travis-ci.org/t-kougei-game-comp/hash)

# 今回の問題

オープンアドレス法のハッシュテーブルの勉強です。

入力される数字を順次格納して、取り出すように指示されたら、要素を取り出してください。

input?.txt ファイルを標準入力として読み込んで、標準出力の結果を output?.txt ファイルと一致するか比較するテストをします。

main.c ファイルだけを書き換えて下さい。

## 入力される値
入力は以下のフォーマットで与えられます。
~~~
a
a
a
a
~~~

aの値に応じて、処理を変えてください。
* 空行: 現在のバッファに格納されている全てのデータをハッシュ値の順に「,」で区切って表示する
* それ以外: 文字列の各文字の文字コードを合計し、その値を10の剰余としてハッシュ値を計算し、格納する。ハッシュ値がすでに使われていたら、1を足した値を新たなハッシュ値とする。ハッシュ値がバッファサイズを超えた場合は、0に戻ってハッシュ値の再計算を行う。

## 期待する出力

空行が入力された際に、その時点のハッシュテーブルを空行区切りで表示します。

最後は改行し、余計な文字、空行を含んではいけません。

## 条件
ハッシュテーブルのサイズは10とします。それ以上に追加しようとしても何も処理されないものとします。

各文字列の文字数は255文字を超えません。

## 入力例1
~~~
a

~~~
* 1行目の文字列は'a'のみで、’a'の文字コードは97のため、7の値のテーブルの位置に文字列は追加されます
* 2行目の値は空行なので、テーブルの中身を表示します。

## 出力例1
~~~
,,,,,,,a,,
~~~

## 入力例2
~~~
a
M2

~~~

## 出力例1
~~~
,,,,,,,a,M2,
~~~
