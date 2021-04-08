---
title: "ファームウェアのインストール"
permalink: /make3d/firmware-installation/
toc: true
---
最初に、Kossel Mini EBを動かすためのファームウェアをインストールします。

Kossel Mini EBでは、Arduino Megaを使用していますので、PCに「Arduino Software」をインストールします。以下のサイトから最新バージョンをダウンロードしてインストールします。

[https://www.arduino.cc/en/Main/Software](https://www.arduino.cc/en/Main/Software){:target="_blank"}

次に、Kossel Mini EBのファームウェアをダウンロードします。ファームウェアはGitHubのEastBackCorporationで公開しています。以下のURLを開いて下さい。

[https://github.com/EastBackCorporation](https://github.com/EastBackCorporation){:target="_blank"}

<figure>
  <img src="{{ '/assets/images/make3d/302/302-1.webp' | relative_url }}" alt="302-1">
</figure>

「Marlin」をクリックして下さい。

<figure>
  <img src="{{ '/assets/images/make3d/302/302-2.webp' | relative_url }}" alt="302-2">
</figure>

画面右側の「Download ZIP」ボタンを押してファイルをダウンロードします。もしGitの使い方を知っている人であれば、コマンドやツールを使ってダウンロードして頂いても構いません。
ダウンロードしたZIPファイルは展開しておきます。

Kossel Mini EBのUSBケーブルをPCに接続します。Kossel Mini EBの電源は特に接続する必要はありません。

Arduino Softwareを起動します。メニューから「ツール」ー「マイコンボード」を選択し、「Arduino/Genuino Mega or Mega 2560」を選択します。

<figure>
  <img src="{{ '/assets/images/make3d/302/302-3.webp' | relative_url }}" alt="302-3">
</figure>

メニューから「ツール」ー「シリアルポート」を選択します。下の写真のように「Arduino/Genuino Mega or Mega 2560」の接続されているポートを選択します。

（写真では「COM3」となっていますが、他のポートの場合もあります。）

<figure>
  <img src="{{ '/assets/images/make3d/302/302-4.webp' | relative_url }}" alt="302-4">
</figure>

メニューから「ファイル」ー「開く」を選択し、展開したファームウェアの中にある「Marlin/Marlin.ino」を選択します。

<figure>
  <img src="{{ '/assets/images/make3d/302/302-5.webp' | relative_url }}" alt="302-5">
</figure>

メニュー下側にある右矢印のボタンを押します。コンパイルが始まり、ファームウェアがArduinoに書き込まれます。書き込みが終了すると、下の写真の様に表示されるようになります。

<figure>
  <img src="{{ '/assets/images/make3d/302/302-6.webp' | relative_url }}" alt="302-6">
</figure>
