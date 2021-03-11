---
title: "コントローラーのインストールと設定"
permalink: /make3d/controller-installation/
toc: true
---
Kossel Mini EBを操作するためのコントローラーをインストールします。

コントローラーは主にKossel Mini EBの初期設定やキャリブレーションで使用します。もし慣れているコントローラーがあれば、そちらを使用されても構いませんが、ここではPrintrunというスイートに含まれるPronterfaceを使用する手順について説明します。以下のサイトからダウンロードしてインストールします。

http://koti.kapsi.fi/~kliment/printrun/

使用しているOSに合わせて最新バージョンをダウンロードします。ダウンロードしたファイルを展開します。展開したフォルダは実行可能な場所に移動させます。Windowsであれば「Program Files (x86)」など、Macであれば「アプリケーション」などです。

Kossel Mini EBのUSBケーブルをPCに接続します。
Pronterfaceを起動します。

メニューの「Settings」をクリックします。「Settings画面」が表示されます。「Printer settingsタブ」の中身を、下の画像の様に変更します。「Serial port」の項目は、Arduino Softwareで接続したポートを設定します。

設定が終わったら、「OK」ボタンを押します。

下の画像の様に、設定が反映されます。

「Connect」ボタンを押すと、Kossel Mini EBに接続されます。「Connect」ボタンが「Disconnect」ボタンに変わり、グレーアウトされていたところが、操作可能な状態になります。

接続が確認できたら「Disconnect」ボタンを押して切断します。
