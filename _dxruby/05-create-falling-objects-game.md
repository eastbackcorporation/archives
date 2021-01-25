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

【プログラムの説明】

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

【プログラムの説明】

- **main.rb**では、プレイヤーのインスタンスを生成（**new**）し、ループ内で、位置の更新（**update**）と描画（**draw**）をしています。
- **player.rb**では、**initialize**メソッド内で、画像や初期位置を設定し、**super**文を使って、スーパークラス（ここでは**Sprite**クラス）のメソッド（ここでは**initialize**メソッド）を呼んでいます。
- プレイヤーの初期位置は、**width**メソッドや、**height**メソッドを使い、画像のサイズを取得して、描画位置を決めています。つまり、画像が変更になっても、ちょうど良い位置に描画されるように考慮してあります。

### プレイヤーの制限
矢印キーで動かしていて気がついたかもしれませんが、ウィンドウの端で消えてしまいます。それ以上移動できないように制限をします。

**player.rb**ファイルを、以下のように書き換えます。

**player.rb**
```ruby
class Player < Sprite
  def initialize()
    image = Image.load("images/noschar1.png")
    x = (640 - image.width) / 2
    y = 400 - image.height
    super(x, y, image)
  end

  def update # 修正
    dx = Input.x
    if (dx == -1 && self.x > 0) || (dx == 1 && self.x < (640 - image.width)) 
      self.x += dx
    end
  end
end
```

プログラムを実行します。左右の矢印キーで、プレイヤーが端で止まるか確認してください。

<figure>
  <img src="{{ '/assets/images/dxruby/05/player2.png' | relative_url }}" alt="Player">
</figure>

【プログラムの説明】

- **Input.x**は、矢印右キーが押されると**1**を返し、矢印左キーが押されると**-1**を返し、それ以外は**0**を返します。ここでは、一旦**dx**変数に値を格納し、**if**文を使って、条件が合った（真）場合のみ、**sefl.x**の値に反省させるようにしています。
- **if**文の条件式には、[論理演算子](/archives/ruby/ruby-spec1/#%E6%BC%94%E7%AE%97){:target="_blank"}を用いています。右端の場合は、プレイヤー画像の幅も考慮しています。

### りんごの作成
落下するりんごを作成します。りんごの落下スピードは、ランダムになるように設定します。

**apple.rb**ファイルを新規作成して、、以下のように書きます。

**apple.rb**
```ruby
class Apple < Sprite
  def initialize()
    image = Image.load("images/apple.png")
    x = rand(0..(640 - image.width))
    y = image.height * -1
    @speed = rand(1..5)
    super(x, y, image)
  end

  def update
    self.y += @speed
    if self.y > 400 - image.height
      self.vanish
    end
  end
end
```

**main.rb**
```ruby
require 'dxruby'

require_relative 'apple' # 追加
require_relative 'player'

Window.bgcolor = [255, 128, 255, 255]
ground_img = Image.new(640, 80, [255, 116, 80, 48])
ground_img.box_fill(0, 0, 640, 10, [255, 0, 128, 0])

apple = Apple.new() # 追加
player = Player.new()


Window.loop do
  Window.draw(0, 400, ground_img)

  apple.update # 追加
  player.update

  apple.draw # 追加
  player.draw
end
```

プログラムを数回実行してください。りんごの落下スピードが違っているか、確認してください。

<figure>
  <img src="{{ '/assets/images/dxruby/05/apple.png' | relative_url }}" alt="Apple">
</figure>

【プログラムの説明】
- **Apple**クラスの**@speed**変数にランダムな整数を入れています。これを落下の時の増分にすることで、早く落ちるりんごやゆっくり落ちるりんごを実現しています。
- **Apple**クラスの**update**メソッドは、りんごが落下して、地面に接触した時、**vanish**メソッドを呼んで、りんごを非表示にしています。

### りんごの複数化
落下するりんごの数を増やします。地面に落下して消えたりんご分の数を新たに作成して、落下させます。

**main.rb**ファイルを、以下のように書き換えます。

**main.rb**
```ruby
require 'dxruby'

require_relative 'apple'
require_relative 'player'

Window.bgcolor = [255, 128, 255, 255]
ground_img = Image.new(640, 80, [255, 116, 80, 48])
ground_img.box_fill(0, 0, 640, 10, [255, 0, 128, 0])

apples = []
apple_n = 5 # 追加
apple_n.times do # 変更
  apples << Apple.new()
end
player = Player.new()

Window.loop do
  Window.draw(0, 400, ground_img)

  Sprite.update(apples) # 変更
  player.update

  Sprite.clean(apples) # 追加
  (apple_n - apples.size).times do # 追加
    apples << Apple.new()
  end

  Sprite.draw(apples)
  player.draw
end
```

実行すると、次々とりんごが落下して、常に5つのりんごがウィンドウに表示されます。

<figure>
  <img src="{{ '/assets/images/dxruby/05/apple2.png' | relative_url }}" alt="Apple">
</figure>

【プログラムの説明】
- 配列**apples**を作成し、複数の*Apple**クラスのインスタンスを入れます。
- **apple_n**を作成して、りんごの表示数**5**を代入しています。こうすることで、数の変更が一箇所で行えます。
- **Sprite.clean**メソッドは、**vanish**メソッドが呼ばれたインスタンスを削除します。
- ループの中で、常に削除されたりんごのインスタンスを補填しています。

### 得点の表示
りんごをキャッチすると、音が鳴って得点が入るようにします。また、得点をウィンドウに表示させます。

プログラムを、以下のように書き換えます。

**player.rb**
```ruby
class Player < Sprite
  attr_accessor :score

  def initialize()
    image = Image.load("images/noschar1.png")
    x = (640 - image.width) / 2
    y = 400 - image.height
    @sound = Sound.new("sounds/get.wav") # 追加
    @score = 0 # 追加
    super(x, y, image)
  end

  def update
    dx = Input.x
    if (dx == -1 && self.x > 0) || (dx == 1 && self.x < (640 - image.width)) 
      self.x += dx
    end
  end

  def shot # 追加
    @sound.play
    @score += 1
  end
end
```

**apple.rb**
```ruby
class Apple < Sprite
  def initialize()
    image = Image.load("images/apple.png")
    x = rand(0..(640 - image.width))
    y = 0
    @speed = rand(1..5)
    super(x, y, image)
  end

  def update
    self.y += @speed
    if self.y > 400 - image.height
      self.vanish
    end
  end

  def hit # 追加
    self.vanish
  end
end
```

**main.rb**
```ruby
require 'dxruby'

require_relative 'apple'
require_relative 'player'

Window.bgcolor = [255, 128, 255, 255]
ground_img = Image.new(640, 80, [255, 116, 80, 48])
ground_img.box_fill(0, 0, 640, 10, [255, 0, 128, 0])
font = Font.new(32) # 追加

apples = []
apple_n = 5
apple_n.times do
  apples << Apple.new()
end
player = Player.new()

Window.loop do
  Window.draw(0, 400, ground_img)

  Sprite.update(apples)
  player.update

  Sprite.check(player, apples) # 追加
  Sprite.clean(apples)
  (apple_n - apples.size).times do
    apples << Apple.new()
  end

  Sprite.draw(apples)
  player.draw

  Window.draw_font(10, 10, "スコア：#{player.score}", font) # 追加
end
```

実行すると、次々とりんごが落下するので、プレイヤーを動かして、りんごをキャッチしてください。得点が加算されるのを確認します。

<figure>
  <img src="{{ '/assets/images/dxruby/05/score.png' | relative_url }}" alt="Apple">
</figure>

【プログラムの説明】
- **Player**クラスに、音用の変数**@sound**, 得点用の変数**@score**を作り、**initialize**メソッド内で初期値を設定しています。
- **Player**クラスに、衝突時に呼ばれる**shot**メソッドを作り、音を鳴らし、得点に加点をしています。
- **Apple**クラスに、衝突時に呼ばれる**hit**メソッドを作り、**vanish**メソッドで表示を消しています。
- **main.rb**のループ内で、**Sprite.check**を使って衝突判定を行っています。
- **main.rb**のループ内で、得点を表示しています。

### 爆弾の作成
このままでは、ゲームは無限に終わりません。爆弾を落下させて、プレイヤーが当たるとゲームが終了するようにします。

プログラムを、以下のように書き換えます。

**player.rb**
```ruby
class Player < Sprite
  attr_accessor :score, :active

  def initialize()
    image = Image.load("images/noschar1.png")
    x = (640 - image.width) / 2
    y = 400 - image.height
    @sound = Sound.new("sounds/get.wav")
    @score = 0
    @active = true
    super(x, y, image)
  end

  def update
    dx = Input.x
    if (dx == -1 && self.x > 0) || (dx == 1 && self.x < (640 - image.width)) 
      self.x += dx
    end
  end

  def shot
    @sound.play
    @score += 1
  end

  def hit
    @active = false
  end
end
```

**bomb.rb**
```ruby
class Bomb < Sprite
  def initialize()
    image = Image.load("images/bomb.png")
    x = rand(0..(640 - image.width))
    y = 0
    @sound = Sound.new("sounds/explosion.wav")
    @speed = rand(1..5)
    super(x, y, image)
  end

  def update
    self.y += @speed
    if self.y > 400 - image.height
      self.vanish
    end
  end

  def shot
    @sound.play
  end
end
```

**main.rb**
```ruby
require 'dxruby'

require_relative 'apple'
require_relative 'bomb'
require_relative 'player'

Window.bgcolor = [255, 128, 255, 255]
ground_img = Image.new(640, 80, [255, 116, 80, 48])
ground_img.box_fill(0, 0, 640, 10, [255, 0, 128, 0])
font = Font.new(32) # 追加

apples = []
apple_n = 5
apple_n.times do
  apples << Apple.new()
end

bombs = []
bomb_n = 5
bomb_n.times do
  bombs << Bomb.new()
end

player = Player.new()

Window.loop do
  Window.draw(0, 400, ground_img)

  if player.active # 追加
    Sprite.update(apples)
    Sprite.update(bombs)
    player.update

    Sprite.check(player, apples)
    Sprite.clean(apples)
    (apple_n - apples.size).times do
      apples << Apple.new()
    end

    Sprite.check(bombs, player) # 追加
    Sprite.clean(bombs) # 追加
    (bomb_n - bombs.size).times do
      bombs << Bomb.new()
    end
  end

  Sprite.draw(apples)
  Sprite.draw(bombs) # 追加
  player.draw

  Window.draw_font(10, 10, "スコア：#{player.score}", font)
end
```

実行すると、りんごと爆弾が落下します。プレイヤーを動かして、りんごをキャッチしながら、爆弾をかわしてください。爆弾に接触するとゲームが停止します。

<figure>
  <img src="{{ '/assets/images/dxruby/05/bomb.png' | relative_url }}" alt="Apple">
</figure>

【プログラムの説明】
- **Bomb**クラスは、ほとんど**Apple**クラスと同じです。違いは、プレイヤーとの衝突時、**shot**メソッドで音を鳴らします。
- **Player**クラスには、プレイヤーの状態を保持する**@active**変数を追加しています。初期値は**true**で、爆弾と接触すると、**hit**メソッドで**false**に変更します。
- **main.rb**では、りんごと同様に、爆弾の初期化やループ内の処理を追加しています。
- プレイヤーが爆弾と接触後、動きを停止させるために、ループ内の**update**、**check**、**clean**の処理を、プレイヤーがアクティブの場合のみに限定しています。

### ゲーム開始、終了
このゲームは、プログラムを起動したらすぐに始まり、ゲームが終了したら動きが止まります。
もう一度ゲームをするには、一度閉じてプログラムを起動しなければなりません。

そこで、スペースキーを押してゲームを開始し、終了したら、再度ゲームを開始するかプログラムを終了するか選択できるようにします。

プログラムを、以下のように書き換えます。

**player.rb**
```ruby
class Player < Sprite
  attr_accessor :score, :active, :game_end

  def initialize()
    image = Image.load("images/noschar1.png")
    x = (640 - image.width) / 2
    y = 400 - image.height
    @sound = Sound.new("sounds/get.wav")
    @score = 0
    @active = false # 変更
    @game_end = false # 追加
    super(x, y, image)
  end

  def update
    dx = Input.x
    if (dx == -1 && self.x > 0) || (dx == 1 && self.x < (640 - image.width)) 
      self.x += dx
    end
  end

  def shot
    @sound.play
    @score += 1
  end

  def hit
    @active = false
    @game_end = true # 追加
  end

  def restart # 追加
    self.x = (640 - image.width) / 2
    self.y = 400 - image.height
    @score = 0
    @active = true
    @game_end = false
  end
end
```

**main.rb**
```ruby
require 'dxruby'

require_relative 'apple'
require_relative 'bomb'
require_relative 'player'

Window.bgcolor = [255, 128, 255, 255]
ground_img = Image.new(640, 80, [255, 116, 80, 48])
ground_img.box_fill(0, 0, 640, 10, [255, 0, 128, 0])
font = Font.new(32)

apples = []
apple_n = 5
apple_n.times do
  apples << Apple.new()
end

bombs = []
bomb_n = 5
bomb_n.times do
  bombs << Bomb.new()
end

player = Player.new()

Window.loop do
  Window.draw(0, 400, ground_img)

  if player.active
    Sprite.update(apples)
    Sprite.update(bombs)
    player.update

    Sprite.check(player, apples)
    Sprite.clean(apples)
    (apple_n - apples.size).times do
      apples << Apple.new()
    end

    Sprite.check(bombs, player)
    Sprite.clean(bombs)
    (bomb_n - bombs.size).times do
      bombs << Bomb.new()
    end
  end

  Sprite.draw(apples)
  Sprite.draw(bombs)
  player.draw

  Window.draw_font(10, 10, "落ち物ゲーム　スコア：#{player.score}", font, {color: C_BLUE})

  if !player.active # 以下追加
    if player.game_end
      Window.draw_font(210, 190, "ゲームオーバー", font, {color: C_BLUE})
    end
    Window.draw_font(120, 282, "スペースキー：ゲームスタート", font, {color: C_BLUE})
    Window.draw_font(181, 314, "ESCキー：ゲーム終了", font, {color: C_BLUE})
    if Input.key_push?(K_SPACE)
      if player.game_end
        apples.map {|apple| apple.vanish}
        Sprite.clean(apples)
        bombs.map {|bomb| bomb.vanish}
        Sprite.clean(bombs)
      end
      player.restart
    elsif Input.key_push?(K_ESCAPE)
      break
    end
  end
end
```

実行すると、スタートか終了のキー入力が表示されます。スペースキーを押すと、ゲームがスタート、または再スタートします。エスケープキーを押すと、ウィンドウが閉じてゲーム終了になります。

<figure>
  <img src="{{ '/assets/images/dxruby/05/start-end.png' | relative_url }}" alt="Apple">
</figure>

<figure>
  <img src="{{ '/assets/images/dxruby/05/start-end2.png' | relative_url }}" alt="Apple">
</figure>

【プログラムの説明】
- **Player**クラスの**@active**変数の初期値を**false**にして、プログラム開始時にゲームスタートしないようにしています。また**@game_end**変数を作り、プレイヤーが爆弾に触れたかどうかを判断するのに使用します。
- **Player**クラスに、**restart**メソットを追加しました。このメソッドを呼ぶと、位置や変数を初期化します。
- **main.rb**のループ内に、プレイヤーの状態によって表示内容や、キー入力などの機能を制御するコードを記入しています。
- 特定のキーが押されているかどうかの判断は、**Input.key_push?**メソッドを使います。キーの種類はこちらから確認できます。
- 配列のメソッド**map**は、配列の各要素への処理を行う場合に使用します。ここでは、すべてのりんごや爆弾に**vanish**メソッドを呼び、次の**Sprite.clean**で、削除しています。
- **Windows.draw_font**メソッドに、文字色（青）を設定しています。

### カスタマイズ
一通りゲームを作ってきました。

本格的なゲームとなると、改善したいところや追加したい機能がいっぱい考えられます。

みなさん、考えてみてください。
