---
title: "コントローラーのインストールと設定"
permalink: /make3d/controller-installation/
toc: true
---
Kossel Mini EBを操作するためのコントローラーをインストールします。

コントローラーは主にKossel Mini EBの初期設定やキャリブレーションで使用します。もし慣れているコントローラーがあれば、そちらを使用されても構いませんが、ここではPrintrunというスイートに含まれるPronterfaceを使用する手順について説明します。以下のサイトからダウンロードしてインストールします。

[http://koti.kapsi.fi/~kliment/printrun/](http://koti.kapsi.fi/~kliment/printrun/){:target="_blank"}

使用しているOSに合わせて最新バージョンをダウンロードします。ダウンロードしたファイルを展開します。展開したフォルダは実行可能な場所に移動させます。Windowsであれば「Program Files (x86)」など、Macであれば「アプリケーション」などです。

<figure>
  <img src="{{ '/assets/images/make3d/303/303-1.webp' | relative_url }}" alt="303-1">
</figure>

Kossel Mini EBのUSBケーブルをPCに接続します。

Pronterfaceを起動します。

<figure>
  <img src="{{ '/assets/images/make3d/303/303-2.webp' | relative_url }}" alt="303-2">
</figure>

メニューの「Settings」をクリックします。「Settings画面」が表示されます。「Printer settingsタブ」の中身を、下の画像の様に変更します。「Serial port」の項目は、Arduino Softwareで接続したポートを設定します。

設定が終わったら、「OK」ボタンを押します。

<figure>
  <img src="{{ '/assets/images/make3d/303/303-3.webp' | relative_url }}" alt="303-3">
</figure>

下の画像の様に、設定が反映されます。

<figure>
  <img src="{{ '/assets/images/make3d/303/303-4.webp' | relative_url }}" alt="303-4">
</figure>

「Connect」ボタンを押すと、Kossel Mini EBに接続されます。「Connect」ボタンが「Disconnect」ボタンに変わり、グレーアウトされていたところが、操作可能な状態になります。

<figure>
  <img src="{{ '/assets/images/make3d/303/303-5.webp' | relative_url }}" alt="303-5">
</figure>

接続が確認できたら「Disconnect」ボタンを押して切断します。
