---
title: "プログラミング言語の概要"
permalink: /ruby/about-programming-languages/
toc: true
---
## ハードウェアとソフトウェア
世の中には機器や機械が溢れています。これらの物理的な「もの」は、**ハードウェア**と言われています。

それに対して、ハードウェア内で、数値計算や情報処理を行うために記述されたもの（プログラム）を**ソフトウェア**と言います。

ソフトウェアを動かすための専用のハードウェアとして、1940年代にコンピュータが作られましたが、コンピュータの小型化・高性能化にともない、あらゆるハードウェアにコンピュータが搭載されるようになりました。

また、1970年代からパソコン（パーソナルコンピュータ）が普及し始め、一般の人でも高度なデータ処理をすることができるようになりました。ワードやエクセルなどの、業務アプリケーションのほか、ゲームなど多くのソフトウェアが作られるようになりました。

それらのソフトウェアを作るための道具（ツール）がプログラミング言語です。当初は、高価なコンピュータでのみ扱うことができましたが、パソコンの普及により、一般の人でも扱えるようになり、さらにインターネットの普及により、安価（または無料）のプログラミング言語やソフトウェア開発環境が簡単に手に入るようになりました。

## アプリケーションソフトウェア
アプリケーションソフトウェア（アプリケーション）は、主に仕事など事務作業で使用するソフトウェアのことを言います（ただし、最近では、ゲームなどを含めてアプリケーション（アプリ）と言ったりします）。

アプリケーションは、大きく分けて２種類あります[^1]。一つは、パソコンなどにインストールして使うタイプのもの、もう一つは、パソコンなどのウェブブラウザを通して使うタイプのものです。前者は**ネイティブアプリ**、後者は**ウェブアプリ**と呼びます。

[^1]: 分類の仕方は他にもいろいろあります。ここでは一つの例として取り上げています。

ネイティブアプリとしては、ワードやエクセルなどの業務アプリのほか、モンストなどスマートフォンにインストールして使うアプリも含みます。

それに対して、ウェブアプリとしては、Googleドキュメントやスプレッドシート、Amazonのショッピングサイト、YouTube、[Scratch](https://scratch.mit.edu/){:target="_blank"}など、ブラウザを通して利用するアプリ（サービス）があります。

## プログラム
ソフトウェアは、人間がプログラムを作成することによって作られます[^2]。プログラミングとは、人間がプログラムを作成する行為です。つまり、プログラミング言語は、プログラムを作成する人間（プログラマー）のための言語で、人間が理解できる言語構成となっています。

[^2]: 人間ではなく、ソフトウェアがソフトウェアを半自動で作る場合もあります。将来的には、完全自動化され人間が作る必要がなくなる時代がやってくるかもしれません。

プログラムは、文字（テキスト）で書かれたファイルです。そのプログラムを**ソースコード（コード）**と呼びます。機械（パソコン）は、テキストで書かれたプログラムを、直接理解することはできません。インタプリタと呼ばれるソフトウェアを使って、プログラムを機械が理解できるデータに変換して使用します。例えば、ワードアプリの実行ファイル（WINWORD.EXE）は、機械が処理するデータ形式となっているため、メモ帳で開くことはできません。このファイルは、ゼロとイチ（０と１）で構成されているので、**バイナリファイル**と呼びます。

## プログラミング言語
世界には、数え切れないほどのプログラミング言語があります。流行り廃りはあるものの、昔から使われているC言語やJava、Javascript、比較的新しいPythonやRubyなどがよく使われています[^3]。

[^3]: [TIOBE index](https://www.tiobe.com/tiobe-index/){:target="_blank"}

プログラム言語には、いくつかの分類方法がありますが、一つの分類として**コンパイラ言語**と**スクリプト（インタープリタ型）言語**とがあります。

コンパイラ言語とは、プログラムを機械が理解できるバイナリ（実行）形式に翻訳（変換）して、そのファイルを配布（インストール）し、実行する言語です。ワードやエクセルなど、パソコンにインストールして利用するアプリに多く利用される言語です。代表的なプログラミング言語は、C言語やJavaです。

スクリプト言語とは、プログラムのコードをそのまま（一行ずつ）実行していく言語です。主にウェブアプリで使用されます。代表的なプログラミング言語は、JavascriptやPython、Rubyです。

コンパイラ言語は、バイナリ形式に翻訳する手間がある一方、実行速度が早い特徴があります。逆にスクリプト言語は、プログラム（テキスト）を書き換えるだけで反映される手軽さがある一方、実行速度はコンパイラ言語より遅くなります。しかし、ハードウェアの性能向上やプログラミング言語の改良によって、スクリプト言語の遅さを感じることは少なくなりました。

これから説明するRubyは、スクリプト言語に分類されます。