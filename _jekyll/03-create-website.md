---
title: "ウェブサイトの作成"
permalink: /jekyll/create-website/
toc: true
---
## Jekyllサイトの作成
ウェブサイト作成の雛形となる**Jekyllサイト**を作成します。

Visual Studio Code（以下、VSCode）を起動し、アプリを置く適当なフォルダ（ここでは**C:/jekyll_lecture/**）を開きます。  
ターミナルを開き、以下のコマンドを実行します。

```bash
jekyll new myblog
```

**myblog**は作成するアプリ名（何でも構いません）です。 

<figure>
  <img src="{{ '/assets/images/jekyll/03/03-1.png' | relative_url }}" alt="03-1">
</figure> 

コマンドの実行が終了すると、VSCodeの左側（エクスプローラー）に**myblog**フォルダが表示されます。展開すると、**postsフォルダ**の他、いくつかファイルが作成されています。

<figure>
  <img src="{{ '/assets/images/jekyll/03/03-2.png' | relative_url }}" alt="03-2">
</figure>

これで、Jekyllサイトの雛形が作成されました。
ターミナルで、**myblog**フォルダに移動し、ウェブサーバーを起動して、ブラウザで動作確認をします。  
ターミナルで、以下のコマンドを実行します。

```bash
cd myblog
jekyll serve
```

<figure>
  <img src="{{ '/assets/images/jekyll/03/03-3.png' | relative_url }}" alt="03-3">
</figure>

コマンドが実行されると、VSCode左側のエクスプローラーに、新しく**_site**フォルダと**.sass-cache**フォルダが作成されます。

<figure>
  <img src="{{ '/assets/images/jekyll/03/03-4.png' | relative_url }}" alt="03-4">
</figure>

ウェブサーバーが起動したら、以下のURLをブラウザで表示させます。

[http://localhost:4000](http://localhost:4000){:target="_blank"}

サンプルページが表示されます。

<figure>
  <img src="{{ '/assets/images/jekyll/03/03-5.png' | relative_url }}" alt="03-5">
</figure>

サンプル記事が1件登録されています。**Welcome to Jekyll!**リンクをクリックして、記事ページを表示させます。

<figure>
  <img src="{{ '/assets/images/jekyll/03/03-6.png' | relative_url }}" alt="03-6">
</figure>

画面右上の**About**をクリックして、Aboutページを表示させます。

<figure>
  <img src="{{ '/assets/images/jekyll/03/03-７.png' | relative_url }}" alt="03-7">
</figure>

ウェブサイトの確認が終わったら、VSCodeのターミナルで**Ctrl + c**（コントロールキーを押しながらCキーを押す）を押して、ウェブサーバーを終了させます。

※ Windowsの場合は「バッチジョブを終了しますか(Y/N)」と表示されますので、再び**Ctrl + c**か**Yの後Enter**で終了させます。

<figure>
  <img src="{{ '/assets/images/jekyll/03/03-8.png' | relative_url }}" alt="03-8">
</figure>

## フォルダとファイルの確認
ここで、Jekyllサイト内のフォルダ・ファイルを確認します。

<figure>
  <img src="{{ '/assets/images/jekyll/03/03-9.png' | relative_url }}" alt="03-9">
</figure>

### _config.yml
サイトの設定ファイルです。デフォルトでは、テーマ**minima**が設定されています[^1]。**title**など、自身のサイトに合わせて書き換えます（HTMLのheader情報に影響します）。

[^1]: minimaテーマ: [https://github.com/jekyll/minima](https://github.com/jekyll/minima){:target="_blank"}

<figure>
  <img src="{{ '/assets/images/jekyll/03/03-10.png' | relative_url }}" alt="03-10">
</figure>

### index.md
トップページ（ランディングページ）のファイルです。  
拡張子が**md**なので、Markdown記法で書かれています。1行目の"\-\-\-"と6行目の"\-\-\-"の間は、設定として使用されます。デフォルトでは、テーマ**minima**で設定されている**home**レイアウトが表示される記述になっています。自身のサイト用に書き換えて使用します。

<figure>
  <img src="{{ '/assets/images/jekyll/03/03-11.png' | relative_url }}" alt="03-11">
</figure>

### about.md
Aboutページのファイルです。  
このようにファイルを配置することで、ページを増やすことができます。

<figure>
  <img src="{{ '/assets/images/jekyll/03/03-12.png' | relative_url }}" alt="03-12">
</figure>

### _posts
ブログなどの記事ファイルを置くフォルダです。  
ウェブサイトのデザインやレイアウトが決まったら、このフォルダに記事を追加して、コンテンツを増やしていきます。

<figure>
  <img src="{{ '/assets/images/jekyll/03/03-13.png' | relative_url }}" alt="03-13">
</figure>

### _site
ウェブサイトの元となる、HTML、CSS、Javascriptファイルや画像、動画ファイルが生成されるフォルダです。  
`jekyll serve`が実行されている場合は、逐次更新されます。手動で生成する場合は、`jekyll build`を実行します。  
Jekyllで作成したサイトを公開する場合は、この**_site**フォルダの中身すべてをウェブサーバーに置きます。

※ GitHub Pagesを使ってサイトを公開する場合は、GitHubのリポジトリを更新するだけで公開されます。

## テーマ
Jekyllのデフォルトテーマは**minima**です。他にも数多くのテーマが公開されています。

・jekyll-theme  
[https://github.com/topics/jekyll-theme](https://github.com/topics/jekyll-theme){:target="_blank"}  
※ GitHubの検索による一覧

・Jamstack Themes  
[https://jamstackthemes.dev/ssg/jekyll/](https://jamstackthemes.dev/ssg/jekyll/){:target="_blank"}

・Jekyll Themes  
[http://jekyllthemes.org/](http://jekyllthemes.org/){:target="_blank"}  
注: httpsではなくhttp

・Jekyll Themes  
[https://jekyllthemes.io/](https://jekyllthemes.io/){:target="_blank"}  

・Jekyll Themes  
[https://jekyll-themes.com/](https://jekyll-themes.com/){:target="_blank"}  

テーマを利用する際は、それぞれのテーマの利用方法や利用制限を確認してください。
