---
title: "落ち物ゲームの作成"
permalink: /dxruby/create-falling-objects-game/
toc: true
---
## falling-objects-gameの作成
[簡単なゲーム作成](/archives/dxruby/create-simple-game/){:target="_blank"}で、DXRubyの基本的な使い方は理解できました。それでは、もう少し難しい落ち物ゲームの作成に挑戦していきます。

新しく出てきた内容（クラスやメソッドなどの仕様）は、[Rubyのリファレンスマニュアル](https://docs.ruby-lang.org/ja/2.7.0/doc/index.html){:target="_blank"}や、[DXRubyのAPIリファレンス](http://mirichi.github.io/dxruby-doc/api/index.html){:target="_blank"}を見て確認しながら進めると、理解が深まります。
{: .notice--info} 

### ゲーム用フォルダの作成
落ち物ゲーム専用のフォルダを作成します。フォルダ名は、**falling-objects-game**とします。

作成したら、**cd**コマンドで移動します。

<figure>
  <img src="{{ '/assets/images/dxruby/05/create-folder.png' | relative_url }}" alt="Create Folder">
</figure>

### 画像・音源の取得
落ち物ゲームで使用する画像と音源は、[yhara](https://twitter.com/yhara){:target="_blank"}氏によって開発された[DXOpal](https://github.com/yhara/dxopal){:target="_blank"}のサンプルプログラムに含まれるものを使います[^1]。

[^1]: DXRubyに似たゲーム開発用フレームワーク。Rubyでブラウザゲームを作るためのライブラリ。MITライセンス。

以下のボタンを押して、画像と音源をダウンロードしてください[^2]。

[<i class="fas fa-download"></i> 画像と音源のダウンロード](https://github.com/eastbackcorporation/dxopal/archive/sample.zip){: .btn .btn--success}

[^2]: リポジトリをフォークしてimages、soundsフォルダのみ残したリポジトリのzipダウンロードリンク

ダウンロードした**dxopal-sample.zip**ファイルを展開して、samplesフォルダ内のapple_catcherフォルダにある**images**フォルダと**sounds**フォルダを、**falling-objects-game**フォルダ内に移動させてください。
