---
title: "Ruby on Railsの概要"
permalink: /rails/about-rails/
toc: true
---
## Ruby on Railsとは
**Ruby on Rails**[^1]（一般的に**Rails**と略されます）とは、プログラミング言語**Ruby**を使った**ウェブアプリケーションフレームワーク**です。

Railsは、デンマーク出身、アメリカ在住の**デイヴィッド・ハイネマイヤー・ハンソン**（David Heinemeier Hansson、通称はDHH）氏[^2]によって開発され、2004年にオープンソースソフトウェアとして公開されました。

[^1]: [Wikiペディア - Ruby on Rails](https://ja.wikipedia.org/wiki/Ruby_on_Rails){:target="_blank"}

[^2]: [Wikiペディア - DHH](https://ja.wikipedia.org/wiki/%E3%83%87%E3%82%A4%E3%83%B4%E3%82%A3%E3%83%83%E3%83%89%E3%83%BB%E3%83%8F%E3%82%A4%E3%83%8D%E3%83%9E%E3%82%A4%E3%83%A4%E3%83%BC%E3%83%BB%E3%83%8F%E3%83%B3%E3%82%BD%E3%83%B3){:target="_blank"}

2005年に、**How to build a blog engine in 15 minutes with Ruby on Rails**[^3]というタイトルの動画をYouTubeに投稿し、話題となりました。タイトル通り、15分で簡単なブログのウェブアプリが作成できます。

[^3]: [YouTube](https://youtu.be/Gzj723LkRJY){:target="_blank"}

以降、急速に世界で知られるようになり、プログラミング言語RubyとともにRailsが世界中で使われ始めました。

## ウェブアプリケーションフレームワークとは
そもそも、ウェブアプリケーションフレームワークとは何でしょうか。

多くの**ウェブサイト**は、**サーバ**と呼ばれるマシン（ハードウェア）上に置かれた**テキストファイル**、**画像ファイル**、**音源ファイル**、**その他メディアファイル**を、**ウェブサーバ**（ソフトウェア）から、インターネットを通して、ウェブブラウザに配信しています。

<figure>
  <img src="{{ '/assets/images/rails/01/web.png' | relative_url }}" alt="Visual Studio Code" class="img_border">
</figure>

**ウェブサイト**の中には、固定の内容を見せるだけではなく、FacebookやTwitterなどのSNSのようにユーザ毎に違う内容を表示させたり、ブログなどの情報を作成・編集・発信したり、ファイルやデータを保存や処理・加工したり、さまざまな機能をもったものがあります。こういったウェブサイトを**ウェブサービス**、**ウェブアプリケーション**と言います。

この、**ウェブアプリケーション**の作成を支援するのが、**ウェブアプリケーションフレームワーク**です。**フレームワーク**とは、日本語で**枠組み**のことです。Railsは、アプリを作る上での枠組みを提供してくれるので、アプリ制作者は、ルールに従って機能などを追加していき、思い通りのアプリケーションを作成します。

多くの**ウェブアプリケーション**は、ユーザ情報などのデータを保存・保持する必要があります。データ保存・処理に使われるのソフトウェアを**データベース**と呼びます。**アプリケーション**と**データベース**との間で、データのやり取りをするには特別な言語[^4]を使う必要があり、一昔前は、専門の人材が必要でした。Railsは、**データベース**とのやり取りも、半自動でできるため、比較的簡単に、素早くウェブアプリケーションの開発が可能です。

[^4]: [Wikiペディア - SQL](https://ja.wikipedia.org/wiki/SQL){:target="_blank"}

そのため、近年では特にベンチャー企業（スタートアップ）などの新興企業・振興サービスに、Railsがよく使われます。

## リファレンス
Ruby on Rails公式ウェブサイト  
[https://rubyonrails.org/](https://rubyonrails.org/){:target="_blank"}

Ruby on Railsチュートリアル  
[https://railstutorial.jp/](https://railstutorial.jp/){:target="_blank"}

Ruby on Railsガイド  
[https://railsguides.jp/](https://railsguides.jp/){:target="_blank"}
