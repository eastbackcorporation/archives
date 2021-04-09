---
title: "スライサーのインストールと設定"
permalink: /make3d/slicer-installation/
toc: true
---
3Dプリントを行う際、3Dモデルデータを3Dプリンターの動作データに変換するソフトウェア、スライサーが必要となります。ここではスライサーのインストールと設定をします。

世の中には数多くのスライサーがオープンソース・ソフトウェアとして公開されています。それぞれに特徴があります。同じ3Dモデルでも、スラーサーによって出来栄えが異なる場合も少くありません。ここでは設定が比較的シンプルなKisslicerというスライサーを使います。以下のサイトからダウンロードしてインストールします。

[http://www.kisslicer.com/download.html](http://www.kisslicer.com/download.html){:target="_blank"}

使用しているOSに合わせて「Kisslicer1.5 Stable」をダウンロードします。ダウンロードしたファイルを展開します。展開したフォルダは実行可能な場所に移動させます。Windowsであれば「Program Files (x86)」など、Macであれば「アプリケーション」などです。

Kossel Mini EBで使用するKisslicer用設定ファイルをダウンロードします。この設定ファイルはGitHubのEastBackCorporationで公開しています。以下のURLを開いて下さい。

[https://github.com/EastBackCorporation](https://github.com/EastBackCorporation){:target="_blank"}

<figure>
  <img src="{{ '/assets/images/make3d/304/304-1.webp' | relative_url }}" alt="304-1">
</figure>

「kossel」をクリックします。

画面右側の「Download ZIP」ボタンを押してファイルをダウンロードします。もしGitの使い方を知っている人であれば、コマンドやツールを使ってダウンロードして頂いても構いません。

ダウンロードしたZIPファイルを展開します。展開したフォルダの中に「kisslicer」フォルダがあります。この中に以下の４つの設定ファイルがあります。

- _materials.ini
- _printers.ini
- _styles.ini
- _supports.ini

このファイルをKisslicerの実行ファイルと同じフォルダに置きます。

Kisslicerを起動します。

<figure>
  <img src="{{ '/assets/images/make3d/304/304-2.webp' | relative_url }}" alt="304-2">
</figure>

初回はダイアログが表示されますので、「Expert」ボタンを押します。

Kisslicerが表示されます。

<figure>
  <img src="{{ '/assets/images/make3d/304/304-3.webp' | relative_url }}" alt="304-3">
</figure>

注意：テーブルが円形になっている事を確認して下さい。四角の場合は、設定ファイルが正しく読み込まれていません。
{: .notice--warning} 

画面右下にある「Show Settings」チェックボックスにチェックを入れます。画面下側に設定が表示されます。

「Style」タブの内容が表示されていると思います。「Style Name」のフィールドに「KosselMiniEB」を表示されている事を確認して下さい。これはダウンロードした設定ファイルが反映されている事を示しています。もし「KosselMiniEB」と表示されていない場合は、設定ファイルを置いた場所が間違っている事が考えられますので、Kisslicerを終了させてから正しいフォルダに設定ファイルを置いて再起動して下さい。

ここで提供している設定はあくまで参考として提供しているもので、必ずしもベストの設定ではありません。使用する素材、素材のメーカーやブランド、造形する3Dモデル、気温や湿度など、様々な条件によって設定値は変わります（変える必要がある場合があります）。実際には自分で工夫して、より綺麗に造形できる条件を見つけていくことになりますし、それが3Dプリンターの楽しみの一つでもあります。

他のタブをクリックして設定内容を確認します。ここで詳しく説明はしませんが、Kisslicerの設定について説明したサイトや資料が公開されていますので、参照しながら確認してみて下さい。

<figure>
  <img src="{{ '/assets/images/make3d/304/304-4.webp' | relative_url }}" alt="304-4">
</figure>
