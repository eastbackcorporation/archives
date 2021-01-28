---
title: "Rubyの基礎"
permalink: /ruby/ruby-basics/
toc: true
---
## Ruby実行環境
Visual Studio Code（以下VSCode）でRubyが実行できるか確認します。

### Ruby実行フォルダ
最初に、Rubyを実行するフォルダを準備します。
どのフォルダでもRubyを実行できますが、ここでは、**C:¥ruby_lecture¥code**フォルダを作成して、**作業フォルダ**とします。

<figure>
  <img src="{{ '/assets/images/ruby/04/working-folder.png' | relative_url }}" alt="Working Folder" class="img_border">
</figure>

### Rubyの実行環境
VSCodeを起動します。

提供しているRubyの実行環境の場合、**C:¥ruby_lecture¥code.bat**をダブルクリックするとVSCodeが起動します。
また、作業フォルダは**C:¥ruby_lecture¥code**に設定されています。
{: .notice--info}

<figure>
  <img src="{{ '/assets/images/ruby/04/vscode-open.png' | relative_url }}" alt="VSCode Open">
</figure>

メニューより、**ファイル** => **フォルダを開く**をクリックします。

<figure>
  <img src="{{ '/assets/images/ruby/04/vscode-folder.png' | relative_url }}" alt="VSCode Folder">
</figure>

**C:¥ruby_lecture¥code**フォルダを選択して、**フォルダの選択**ボタンをクリックします。

<figure>
  <img src="{{ '/assets/images/ruby/04/vscode-folder2.png' | relative_url }}" alt="VSCode Folder">
</figure>

VSCodeの左側の**エクスプローラー**に**code**フォルダが表示されます。

<figure>
  <img src="{{ '/assets/images/ruby/04/vscode-folder3.png' | relative_url }}" alt="VSCode Folder">
</figure>

ここには、Windowsのエクスプローラーと同様に、フォルダやファイルがツリー表示されます。

メニューより、**ターミナル** => **新しいターミナル**をクリックします。

<figure>
  <img src="{{ '/assets/images/ruby/04/vscode-terminal.png' | relative_url }}" alt="VSCode Terminal">
</figure>

VSCodeの下側にターミナル（コマンドプロンプト）が表示されます。

<figure>
  <img src="{{ '/assets/images/ruby/04/vscode-terminal2.png' | relative_url }}" alt="VSCode Terminal">
</figure>

Rubyが実行できるか、確認します。
ターミナルに
```bash
ruby -v
```
と入力して、**Enter**キーを押します。Rubyのバージョンが表示されます。

<figure>
  <img src="{{ '/assets/images/ruby/04/vscode-ruby-version.png' | relative_url }}" alt="VSCode Ruby Version">
</figure>

## Hello World
**Hello World**と画面に出力する簡単なRubyのプログラムを書いて実行します。

### プログラムファイル作成
エクスプローラーの**code**の右側にマウスカーソルを移動させると表示される、**新しいファイル**アイコンをクリックします。

<figure>
  <img src="{{ '/assets/images/ruby/04/vscode-new-file.png' | relative_url }}" alt="VSCode New File">
</figure>

ファイル名の入力状態になりますので、`hello.rb`と入力して、Enterキーを押します。

<figure>
  <img src="{{ '/assets/images/ruby/04/vscode-new-file2.png' | relative_url }}" alt="VSCode New File">
</figure>

プログラムファイルは、テキストファイルです。拡張子は何でも（.txtでも）よいですが、Rubyのプログラムだと分かるように慣例的に<strong>.rb</strong>とします。
{: .notice--info}

**hello.rb**ファイルが作成され、**hello.rb**ファイルが開きます。

<figure>
  <img src="{{ '/assets/images/ruby/04/vscode-new-file3.png' | relative_url }}" alt="VSCode New File">
</figure>

**hello.rb**ファイルに、
```ruby
puts "Hello World!"
```
と入力します。

<figure>
  <img src="{{ '/assets/images/ruby/04/vscode-program.png' | relative_url }}" alt="VSCode Program">
</figure>

メニューより、**ファイル** => **保存**をクリックして保存します。

<figure>
  <img src="{{ '/assets/images/ruby/04/vscode-program2.png' | relative_url }}" alt="VSCode Program">
</figure>

ファイルの保存は、ショートカットキー（Ctrl + s：コントロールキーを押しながらsキーを押す）を使用して保存するやり方が簡単です。
{: .notice--info}

ファイル名のタブの右側に丸（●）がある場合は、変更が保存されていない状態です。保存するとバッテン（✕）になります。
{: .notice--info}

### プログラムの実行
Rubyのプログラムを実行するには、**ruby**コマンドを使います。`ruby`の後に半角スペース、その後にプログラムファイル名を入力して実行します。

ターミナルで、
```bash
ruby hello.rb
```
と入力して、**Enterキー**を押します。

ターミナルに、
```bash
Hello World!
```
と表示されているのを確認します。

<figure>
  <img src="{{ '/assets/images/ruby/04/vscode-program3.png' | relative_url }}" alt="VSCode Program">
</figure>

次に、**hello.rb**ファイルを、
```ruby
puts "Hello World!ハロールビー！"
```
と編集して、保存・実行してみてください。

<figure>
  <img src="{{ '/assets/images/ruby/04/vscode-program4.png' | relative_url }}" alt="VSCode Program">
</figure>

また、プログラムを、
```ruby
puts "Hello World!"
puts "ハロールビー！"
puts "私はRubyが好きです。"
```
など、文字を変えたり、行を増やしてみてください。

`puts`は画面（標準出力）に文字（と改行）を表示する関数のようなもの（Rubyではメソッドと呼びます）です。  
また、文字（文字列）は、ダブルクォーテーション`"`で囲みます。
{: .notice--info}

## 計算と入出力
入力した数値を計算して出力するプログラムを書いて実行します。

### 数値の出力
`calculation.rb`という名前のファイルを作成します。

<figure>
  <img src="{{ '/assets/images/ruby/04/vscode-calc.png' | relative_url }}" alt="VSCode calculation.rb">
</figure>

`puts`の後に、足し算を記入して実行します。
```ruby
puts 5 + 3
```

Rubyは、全角・半角、大文字・小文字を区別します。大文字の数字は**数値**として扱いません。
{: .notice--warning}

実行すると、計算結果が表示されます。
```bash
8
```

<figure>
  <img src="{{ '/assets/images/ruby/04/vscode-calc2.png' | relative_url }}" alt="VSCode calculation.rb">
</figure>

`5 + 3 = 8`の様に表示させたいと思います。以下のように書き換えてください。
```ruby
puts 5 + 3 = 8
```

実行すると、エラーになりました。
```bash
syntax error, unexpected '=', expecting end-of-input
puts 5 + 3 = 8
```

<figure>
  <img src="{{ '/assets/images/ruby/04/vscode-calc3.png' | relative_url }}" alt="VSCode calculation.rb">
</figure>

**syntax error**は、書き方がRubyの規則に合ってない場合に表示されるエラーです。
{: .notice--info}

`5 + 3 = 8`の全体を`"`で囲い、文字列にします。以下のように書き換えてください。

```ruby
puts "5 + 3 = 8"
```

実行すると、
```bash
5 + 3 = 8
```
と表示されました。

<figure>
  <img src="{{ '/assets/images/ruby/04/vscode-calc3-2.png' | relative_url }}" alt="VSCode calculation.rb">
</figure>

まとめると、
- `"`で囲んだ文字（文字列と言います）は表示できる。
- 計算式は結果（数値）が表示される。
となります。

式と結果を両方表示させたい場合は、どうしたらよいでしょうか。

Rubyでは、文字列の中に数値（計算結果）を埋め込むことができます。以下のように書き換えてください。
```ruby
puts "5 + 3 = #{5 + 3}"
```

実行すると、
```bash
5 + 3 = 8
```
エラーなく表示されます。

<figure>
  <img src="{{ '/assets/images/ruby/04/vscode-calc4.png' | relative_url }}" alt="VSCode calculation.rb">
</figure>

`#{式}`は**式展開**と呼びます。**式**の計算結果を文字列に変換します。
{: .notice--info}

### 変数と代入
Rubyでは、数学と同様に変数を扱うことができます。ここでは、xとyを使います。

変数の代入は、**変数 = 値**という書き方をします（左辺に変数、右辺に値や計算結果など）。

以下のように書き換えてください。
```ruby
x = 5
y = 3
puts "#{x} + #{y} = #{x + y}"
```

Rubyは、プログラムファイルの上の行から順番に処理を行います。
{: .notice--info}

実行すると、
```bash
5 + 3 = 8
```
同じ結果が表示されます。

<figure>
  <img src="{{ '/assets/images/ruby/04/vscode-calc5.png' | relative_url }}" alt="VSCode calculation.rb">
</figure>

Rubyでは、変数も**式**として扱うことができます。変数の演算は、中の数値に対して行われます。
{: .notice--info}

x、yの値を実数に書き換えて実行します。
```ruby
x = 3.1415
y = 1.2
puts "#{x} + #{y} = #{x + y}"
```

実行すると、
```bash
3.1415 + 1.2 = 4.3415
```
正しい実数の計算結果が表示されます。

<figure>
  <img src="{{ '/assets/images/ruby/04/vscode-calc6.png' | relative_url }}" alt="VSCode calculation.rb">
</figure>

### キー入力
変数x、yは、プログラム中で固定の値を代入していました。今度は、キーボードから入力した値を計算して出力するようにします。

Rubyには、キーボードからの入力を受け付けるメソッド`gets`があります。このメソッドは、Enterキーが押されるまでのキー入力を記憶し、Enterキーが押された時にキー入力を（改行を含んだ）文字列として返します。

改行は、改行コードという特殊な文字（Windowsの場合は¥r¥n）として扱われます。改行コードが不要な場合は、文字列末尾の改行コードを削除するメソッド`chomp`を使います。

また、ここでは、文字列ではなく数値として扱いたいので、文字列を数値（整数）に変換するメソッド`to_i`を使います。

プログラムを、以下のように書き換えてください。
```ruby
x = gets
x = x.chomp
x = x.to_i

y = gets
y = y.chomp
y = y.to_i

puts "#{x} + #{y} = #{x + y}"
```

実行してみます。数値（整数）を入力してEnterキーを押します。
```bash
5
3
5 + 3 = 8
```
正しい計算結果が表示されます。

<figure>
  <img src="{{ '/assets/images/ruby/04/vscode-calc7.png' | relative_url }}" alt="VSCode calculation.rb">
</figure>

このプログラムでは、プログラムが止まっているように見えるので、プログラムの意図を知らない人は、何をしてよいか分かりません。

説明を表示するように修正します。

プログラムを、以下のように書き換えてください。
```ruby
puts "このプログラムは整数の加算（x + y）を計算して結果を表示します。"

print "変数xの値（整数）を入力してください："
x = gets
x = x.chomp
x = x.to_i

print "変数yの値（整数）を入力してください："
y = gets
y = y.chomp
y = y.to_i

puts "#{x} + #{y} = #{x + y}"
```

**print**メソッドは、**puts**メソッドと同じく、文字列を出力しますが、最後に改行をつけません。
{: .notice--info}

<figure>
  <img src="{{ '/assets/images/ruby/04/vscode-calc8.png' | relative_url }}" alt="VSCode calculation.rb">
</figure>

説明が表示されるので、分かりやすいプログラムになりました。

### メソッド
メソッドとは、数学で言う**関数**のようなもので、処理をした結果（値など）を返します。

**puts**メソッド
- 処理：文字列（改行付き）を、画面に表示する。
- 結果：なし

**gets**メソッド
- 処理：キーボード入力を記憶する。
- 結果：記憶した文字列（改行付き）

Rubyのメソッドには、**もの**に対して働きかける（処理をする）ものがあります。
書式は、**もの.メソッド**のように、<strong>.（ドット）</strong>でつなぎます。
ここで言う**もの**を、**オブジェクト**と呼びます。

**chomp**メソッド
- 処理：オブジェクト（文字列）の行末の改行を削除する。
- 結果：処理結果（文字列）

**to_i**メソッド
- 処理：オブジェクト（文字列）を整数に変換する。
- 結果：処理結果（整数）

実は、**puts**メソッドや**gets**メソッドは、**オブジェクト**と<strong>.（ドット）</strong>が省略されています。
このように、単独で使うメソッドは**関数的メソッド**と呼びます。
{: .notice--info}

また、メソッドは結合して使うこともできます。上記のプログラムは、以下のように短く書き直すことができます。

```ruby
puts "このプログラムは整数の加算（x + y）を計算して結果を表示します。"

print "変数xの値（整数）を入力してください："
x = gets.chomp.to_i

print "変数yの値（整数）を入力してください："
y = gets.chomp.to_i

puts "#{x} + #{y} = #{x + y}"
```

プログラムを実行してみると、同じように動作します。

### コメント
プログラム中に説明やメモを書くことができます。それをコメントと呼びます。Rubyは、コメントを無視して処理を進めます。

**#**（ハッシュ）を書くと、同じ行のそれ以降はコメントとして扱われます。また、行頭に書いた**=begin**と**=end**に囲まれた行（複数行）はコメントとして扱われます。
```ruby
# これは１行すべてコメントです。
x = 5 # 行の途中からコメントにもできます。

=begin
この間は、
すべて
コメント
に
なります。
=end

y = 3
```

それでは、上記のプログラムにプログラムの説明をコメントで入れます。

```ruby
# プログラム名：加算プログラム（calculation.rb）
# 説明：整数xとyを入力し、式とともに結果を出力する。

puts "このプログラムは整数の加算（x + y）を計算して結果を表示します。"

print "変数xの値（整数）を入力してください："
x = gets.chomp.to_i

print "変数yの値（整数）を入力してください："
y = gets.chomp.to_i

puts "#{x} + #{y} = #{x + y}"
```

<figure>
  <img src="{{ '/assets/images/ruby/04/vscode-calc9.png' | relative_url }}" alt="VSCode calculation.rb">
</figure>

プログラムを実行してください。コメントは無視されるので、問題なく実行されます。
