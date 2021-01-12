---
title: "Rubyの基礎"
permalink: /ruby/ruby-basics/
toc: true
---
## Hello World
**Hello World**と画面に出力する簡単なRubyのプログラムを書いて実行します。

### Ruby実行フォルダ
最初に、Rubyを実行するフォルダを準備します。
どのフォルダでもRubyを実行できますが、ここでは、**C:¥ruby_lecture¥code**フォルダを作成して、作業フォルダとします。

<figure>
  <img src="{{ '/assets/images/ruby/04/working-folder.png' | relative_url }}" alt="Working Folder">
</figure>

### Rubyの実行環境
Visual Studio Code（以下VSCode）を起動します。

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

### プログラムファイル作成
エクスプローラーの**code**の右側にマウスカーソルを移動させると表示される、**新しいファイル**アイコンをクリックします。

<figure>
  <img src="{{ '/assets/images/ruby/04/vscode-new-file.png' | relative_url }}" alt="VSCode New File">
</figure>

ファイル名の入力状態になりますので、`hello.rb`と入力して、Enterキーを押します。

<figure>
  <img src="{{ '/assets/images/ruby/04/vscode-new-file2.png' | relative_url }}" alt="VSCode New File">
</figure>

プログラムファイルは、テキストファイルです。拡張子は何でも（.txtでも）よいですが、Rubyのプログラムだと分かるように慣例的に.rbとします。
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

### Rubyの実行
ターミナルで、
```bash
ruby hello.rb
```
と入力して、**Enterキー**を押します。

Rubyのプログラムを実行するには、**ruby**コマンドを使います。`ruby`の後に半角スペース、その後にプログラムファイル名を入力して実行します。
{: .notice--info}

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

何となく分かってきたかもしれませんが、`puts`は画面（標準出力）に文字（と改行）を表示する関数（メソッド）です。  
また、文字（文字列）は、ダブルクォーテーション`"`で囲みます。
{: .notice--info}
