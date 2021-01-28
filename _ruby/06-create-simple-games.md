---
title: "簡単なゲームの作成"
permalink: /ruby/create-simple-games/
toc: true
---
## 数当てゲーム
数当てゲームのプログラムを作成します。この数当てゲームは、最初、プログラム内でランダムな数を生成します。プレイヤーは、その数を予測して入力します。

プログラムは、正解値と入力値を比較して、入力値が大きければ**正解は入力値より小さいです。**と表示し、入力値が小さければ**正解は入力値より大きいです。**と表示します。
正解値と入力値が同じにであれば**正解です。**と表示します。

正解になるまで、何度も繰り返します。

### プログラムファイルの作成
プログラムのファイル名を**number_guessing_game.rb**として、作成します。

<figure>
  <img src="{{ '/assets/images/ruby/06/create-file.png' | relative_url }}" alt="VSCode Ruby Version">
</figure>

### ランダムな数の生成
Rubyには、ランダムな整数を生成する**rand**メソッドが用意されています。

```ruby
rand(0) # 0.0から1.0未満の間の実数をランダムに生成
rand(10) # 0から9の間の整数をランダムに生成
rand(1..10) #1から10の間の整数をランダムに生成
```

より詳しく知りたい人は、Rubyリファレンスマニュアルの[rand](https://docs.ruby-lang.org/ja/2.7.0/class/Kernel.html#M_RAND){:target="_blank"}を参照してください。
{: .notice--info}

ここでは、1から100の間の整数を生成することにします。生成した整数は、変数**seikai**に代入します。

```ruby
seikai = rand(1..100)
```

想定通りに動作するか、生成した値を表示させて確認します。プログラムを、以下のように書いてください。

```ruby
seikai = rand(1..100)
puts seikai
```

プログラムを実行します。

```bash
ruby number_guessing_game.rb
```

1から100の間の整数が表示されます。

```bash
86
```

<figure>
  <img src="{{ '/assets/images/ruby/06/rand.png' | relative_url }}" alt="VSCode Ruby Version">
</figure>

何度か実行を繰り返してみてください。

### プレーヤーの値入力
プレーヤーが値を入力するプログラムを書きます。[Rubyの基礎 - メソッド](/archives/ruby/ruby-basics/#%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89){:target="_blank"}のプログラムを参考にします。入力した整数は、変数**kaitou**に代入します。

**puts seikai**は、コメントにして（コメントアウトと言います）実行されないようにします。

```ruby
seikai = rand(1..100)
# puts seikai

print "正解と思う整数を入力してください："
nyuryoku = gets.chomp.to_i
puts nyuryoku
```

実行すると、
```bash
正解と思う整数を入力してください：55
55
```
入力した整数が正しく表示されました。

<figure>
  <img src="{{ '/assets/images/ruby/06/input.png' | relative_url }}" alt="VSCode Ruby Version">
</figure>

### 条件分岐
正解値と入力値を比較して、結果を表示するプログラムを書きます。[Rubyの言語仕様1 - 条件分岐](/archives/ruby/ruby-spec1/#%E6%9D%A1%E4%BB%B6%E5%88%86%E5%B2%90){:target="_blank"}の説明を参考にします。

いろいろな書き方ができますので、自分なりに考えてみてください。

プログラムが正しいか判断するため、**puts seikai**のコメントを外して、正解値を表示します。

**puts nyuryoku**は不要なので、削除します。

```ruby
seikai = rand(1..100)
puts "正解：#{seikai}"

print "正解と思う整数を入力してください："
nyuryoku = gets.chomp.to_i

if seikai < nyuryoku
  puts "正解は入力値より小さいです。"
elsif seikai > nyuryoku
  puts "正解は入力値より大きいです。"
else
  puts "正解です。"
end
```

正しく表示されるか、複数回実行して確認してください。

```bash
正解：21
正解と思う整数を入力してください：21
正解です。

正解：35
正解と思う整数を入力してください：34
正解は入力値より大きいです。
```

<figure>
  <img src="{{ '/assets/images/ruby/06/condition.png' | relative_url }}" alt="VSCode Ruby Version">
</figure>

### 繰り返し
上記のプログラムでは、1回入力したら終了してしまいます。繰り返して入力できるようにします。

ここでは、**while**文を使うこととします。

**hazure**変数に初期値として**true**を代入しておき、**while**文の条件式に使います。

正解時、**hazure**変数を**false**に変更します。次の条件式の評価で**false**となり、繰り返しが終了します。

プレイヤーの入力と結果表示のコードを**while〜end**で囲みます。

```ruby
seikai = rand(1..100)
puts "正解：#{seikai}"

hazure = true

while hazure
  print "正解と思う整数を入力してください："
  nyuryoku = gets.chomp.to_i

  if seikai < nyuryoku
    puts "正解は入力値より小さいです。"
  elsif seikai > nyuryoku
    puts "正解は入力値より大きいです。"
  else
    puts "正解です。"
    hazure = false
  end
end
```

**while〜end**の中に入るコードの行の先頭に半角スペース2個を入れて、**字下**げしています。これを**インデント**と呼びます。
適切にインデントを入れると、プログラムが読みやすくなります。
{: .notice--info}

```bash
正解：88
正解と思う整数を入力してください：70
正解は入力値より大きいです。
正解と思う整数を入力してください：90
正解は入力値より小さいです。
正解と思う整数を入力してください：88
正解です。
```

正解するとプログラムが終了します。

<figure>
  <img src="{{ '/assets/images/ruby/06/loop.png' | relative_url }}" alt="VSCode Ruby Version">
</figure>

### 仕上げ
プログラムは、想定通りに動作しました。最後に仕上げをします。

- 確認用の正解値表示をコメントアウトする。
- プログラム実行直後、ゲーム名と遊び方を表示する。
- ファイルの先頭に、プログラム名と説明を追加する。

```ruby
# プログラム名：数当てゲーム（number-guessing-game.rb）
# 説明：ランダム生成した整数を予測して当てるゲーム

puts "数当てゲーム"
puts "1から100までの整数をランダム生成します。その数を当ててください。"

seikai = rand(1..100)
# puts "正解：#{seikai}"

hazure = true

while hazure
  print "正解と思う整数を入力してください："
  nyuryoku = gets.chomp.to_i

  if seikai < nyuryoku
    puts "正解は入力値より小さいです。"
  elsif seikai > nyuryoku
    puts "正解は入力値より大きいです。"
  else
    puts "正解です。"
    hazure = false
  end
end
```

実行してみて、問題なく動作すればプログラムの完成です。

### プログラムの改良
この**数当てゲーム**を改良してみましょう。

1. 何回目の入力で正解したか表示する。
2. 正解した後、もう一度最初から始めるか、やめるか選択できるようにする。
3. 正解値の上限100を変更（プレイヤーが指定）できるようにする。
