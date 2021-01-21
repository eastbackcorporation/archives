---
title: "サンプルの実行"
permalink: /dxruby/dxruby-samples/
toc: true
---
## サンプルプログラム
DXRubyには、多数のサンプルプログラムが用意されています。

サンプルは、DXRubyのソースコードとともに公開されています[^1]。

[^1]: [GitHubリポジトリ](https://github.com/mirichi/dxruby){:target="_blank"}のsampleフォルダ

ここでは、サンプルプログラムのみダウンロードできるようにしていますので、それを使います。

## サンプルのダウンロード
以下のボタンを押して、サンプルプログラムをダウンロードしてください[^2]。

[<i class="fas fa-download"></i> DXRubyサンプルのダウンロード](https://github.com/eastbackcorporation/dxruby/archive/sample.zip){: .btn .btn--success}

[^2]: リポジトリをフォークしてsampleフォルダのみ残したリポジトリのzipダウンロードリンク

<figure>
  <img src="{{ '/assets/images/dxruby/03/sample-download.png' | relative_url }}" alt="DXRuby Sample Download" class="img_border">
</figure>

ダウンロードが完了したら、同じ場所に展開してください。

<figure>
  <img src="{{ '/assets/images/dxruby/03/sample-unzip.png' | relative_url }}" alt="DXRuby Sample Unzip" class="img_border">
</figure>

**dxruby-sample**フォルダをクリックして、表示される**dxruby-sample**フォルダを再度クリックすると、**sample**フォルダが表示されます。

<figure>
  <img src="{{ '/assets/images/dxruby/03/sample-folder.png' | relative_url }}" alt="DXRuby Sample Folder" class="img_border">
</figure>

この**sample**フォルダを、Rubyの作業フォルダ（**C:¥ruby_lecture¥code**）に移動させてください。

<figure>
  <img src="{{ '/assets/images/dxruby/03/sample-folder2.png' | relative_url }}" alt="DXRuby Sample Folder" class="img_border">
</figure>

## サンプルの実行
Visual Studio Code（以下VSCode）を起動します。左側のツリーに**sample**フォルダが表示されています。

**sample**フォルダをクリックすると５つのサンプルフォルダが展開されて表示されます。最初に、**new_sample**フォルダをクリックして、展開してください。

<figure>
  <img src="{{ '/assets/images/dxruby/03/vscode-sample.png' | relative_url }}" alt="VSCode">
</figure>

展開されたファイルの中から**rubima.rb**ファイルをクリックして、ファイルの中を表示させます。
スクロールしてプログラムコードを見てください（最後のコードまで、596行あります）。

<figure>
  <img src="{{ '/assets/images/dxruby/03/rubima.png' | relative_url }}" alt="VSCode">
</figure>

おそらく、何が書かれているか分からないでしょう（ぱっと見て理解できる人は、この世の中にいないと思います）。

このプログラムを実行してみましょう。

コマンドプロンプトを見ると、今いる場所は**C:¥ruby_lecture¥code**になっています。**cd**コマンドを使って**rubima.rb**ファイルの場所まで移動します。

コマンドプロンプトに以下を入力します。

```bash
cd sample¥new_sample
```

Windowsでは、**¥**と**\\（バックスラッシュ）**は同じ記号です。**¥キー**を押して入力します。
{: .notice--info} 

**cd**コマンドで、一つ上のフォルダに移動するには、`cd ..`のように、ドット2つを入力します。
{: .notice--info} 

<figure>
  <img src="{{ '/assets/images/dxruby/03/cd-command.png' | relative_url }}" alt="cd command">
</figure>

コマンドプロンプトで、ファイルやフォルダの一覧を見るには**dir**コマンドを使います。

コマンドプロンプトに以下を入力します。

```bash
dir
```

一覧の中に**rubima.rb**ファイルがあることを確認します。

<figure>
  <img src="{{ '/assets/images/dxruby/03/dir-command.png' | relative_url }}" alt="cd command">
</figure>

それでは、サンプルプログラム**rubima.rb**を実行します。

コマンドプロンプトに以下を入力します。

```bash
ruby rubima.rb
```

<figure>
  <img src="{{ '/assets/images/dxruby/03/rubima-exec.png' | relative_url }}" alt="cd command">
</figure>

しばらくすると、別のウィンドウが表示されて、**るびまサンプルゲーム**が開始されます。

<figure>
  <img src="{{ '/assets/images/dxruby/03/rubima1.png' | relative_url }}" alt="cd command">
</figure>

画面下側中央にあるのが自機（プレイヤー）です。画面上側からやってくるのが敵と敵の弾です。

**操作方法**  
- 矢印キー（4方向）：自機の移動
- Zキー：自機の弾発射（連射可能）
- ESCキー：ゲームの終了

<figure>
  <img src="{{ '/assets/images/dxruby/03/rubima2.png' | relative_url }}" alt="cd command">
</figure>

同じ要領（cdコマンドで移動、rubyコマンドで実行）で、他のサンプルプログラムも実行してみてください。
