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

ダウンロードした**dxopal-sample.zip**ファイルを展開します。

**samples**フォルダ内の**apple_catcher**フォルダにある**images**フォルダと**sounds**フォルダを、**falling-objects-game**フォルダ内に移動させてください。

<figure>
  <img src="{{ '/assets/images/dxruby/05/image-sound-folders.png' | relative_url }}" alt="Image Sound Folders" class="img_border">
</figure>

<figure>
  <img src="{{ '/assets/images/dxruby/05/image-sound-folders2.png' | relative_url }}" alt="Image Sound Folders">
</figure>

### main.rb作成
最初に、**main.rb**ファイルを作成し、基本となるウィンドウ表示用のプログラムを書いて実行してみます。

**main.rb**ファイルに、以下のように書いてください。

```ruby
require 'dxruby'

Window.loop do
end
```

コマンドプロンプトに以下を入力して、プログラムを実行します。

```bash
ruby main.rb
```

<figure>
  <img src="{{ '/assets/images/dxruby/05/main.rb.png' | relative_url }}" alt="main.rb">
</figure>

ウィンドウが表示されることを確認します。

<figure>
  <img src="{{ '/assets/images/dxruby/05/main.rb2.png' | relative_url }}" alt="main.rb">
</figure>

### 背景の作成
背景が全面黒では寂しいですね。背景に地面と空を描きます。

DXRubyのImageクラスは、既存の画像を扱うだけでなく、線、円、三角、四角を描画するメソッドが用意されています。

ここでは、背景を空色に塗り、茶色と緑色を使った地面を配置します。

**main.rb**ファイルに、以下のように書き加えます。

```ruby
require 'dxruby'

Window.bgcolor = [255, 128, 255, 255] # 追加
ground_img = Image.new(640, 80, [255, 116, 80, 48]) # 追加
ground_img.box_fill(0, 0, 640, 10, [255, 0, 128, 0]) # 追加

Window.loop do
  Window.draw(0, 400, ground_img) # 追加
end
```

プログラムを実行します。ウィンドウに背景が表示されます。

<figure>
  <img src="{{ '/assets/images/dxruby/05/background.png' | relative_url }}" alt="Background">
</figure>

プログラムの説明をします。

- **Window.bgcolor**で、ウィンドウのバックグラウンドカラーを指定します。色は[ARGB配色](http://mirichi.github.io/dxruby-doc/api/constant_color.html){:target="_blank"}に従って指定します。
- **Image.new**メソッドで、Imageクラスのインスタンス（地面）を生成します。引数にザイズ、色（茶色）を指定しています。
- **box_fill**メソッドは、上記Imageインスタンスの画像に色指定（緑色）の四角を描画（上書き）しています。
- **Window.draw**では、ウィンドウ上の(0, 400)の位置に地面を描画しています。

### プレイヤーの作成
プレイヤーを作成します。[簡単なゲーム作成](/archives/dxruby/create-simple-game/){:target="_blank"}では、4方向に移動できるようにしましたが、落ち物ゲームでは、左右にのみ動けるようにします。

**player.rb**ファイルを新規作成し、**main.rb**ファイルに書き加えます。

**player.rb**
```ruby
class Player < Sprite
  def initialize()
    image = Image.load("images/noschar1.png")
    x = (640 - image.width) / 2
    y = 400 - image.height
    super(x, y, image)
  end

  def update
    self.x += Input.x
  end
end
```

**main.rb**
```ruby
require 'dxruby'

require_relative 'player' # 追加

Window.bgcolor = [255, 128, 255, 255] # 追加
ground_img = Image.new(640, 80, [255, 116, 80, 48]) # 追加
ground_img.box_fill(0, 0, 640, 10, [255, 0, 128, 0]) # 追加

player = Player.new() # 追加

Window.loop do
  Window.draw(0, 400, ground_img) # 追加

  player.update # 追加
  player.draw # 追加
end
```

プログラムを実行します。左右の矢印キーで、プレイヤーが動くか確認してください。

<figure>
  <img src="{{ '/assets/images/dxruby/05/player.png' | relative_url }}" alt="Player">
</figure>

プログラムの説明をします。

- **main.rb**では、プレイヤーのインスタンスを生成（**new**）し、ループ内で、位置の更新（**update**）と描画（**draw**）をしています。
- **player.rb**では、**initialize**メソッド内で、画像や初期位置を設定し、**super**構文を使って、スーパークラス（ここでは**Sprite**クラス）のメソッド（ここでは**initialize**メソッド）を呼んでいます。
- プレイヤーの初期位置は、**width**メソッドや、**height**メソッドを使い、画像のサイズを取得して、描画位置を決めています。つまり、画像が変更になっても、ちょうど良い位置に描画されるように考慮してあります。

