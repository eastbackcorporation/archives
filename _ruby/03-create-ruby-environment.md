---
title: "Rubyの実行環境構築"
permalink: /ruby/create-ruby-environment/
toc: true
---

期間限定（2021/1/15〜2021/2/28）で、DXRubyが使用できるRubyの実行環境(Windows版)をzipで提供します。
{: .notice--warning}

[<i class="fas fa-download"></i> Ruby実行環境のダウンロード](https://download.eastback.co.jp/minamiko/ruby_lecture.zip){: .btn .btn--success}

上記ボタンをクリックするとダウンロードが始まります。
ダウンロードした**ruby_lecture.zip**を、Cドライブ直下に展開してください。エクスプローラーで`C:¥ruby_lecture¥code.bat`をダブルクリックすると、Visual Studio Codeが起動します。

- Ruby: RubyInstaller for Windows Ruby+Devkit 2.7.2-1 (x64) （DXRuby 1.4.7 インストール済み）
- IDE: Visual Studio Code 1.52.1 （.zip 64bit）
- 作業フォルダ: **C:¥ruby_lecture¥code**

## Rubyの実行環境
Rubyのプログラムを実行するためには、パソコンにRubyをインストールする必要があります。

Windows10には、Rubyをインストールするためのアプリケーションがいくつかありますが、ここでは[RubyInstaller for Windows](https://rubyinstaller.org/){:target="_blank"}（無料）というアプリを使用します。他のアプリと同様な手順で、簡単にRubyをインストールすることができます。

Macには、最初からRubyがインストールされています[^1]。

[^1]: Rubyのバージョンが古く固定されているので、複数のバージョンをインストールしたり、切り替えることのできる[rbenv](https://github.com/rbenv/rbenv){:target="_blank"}や[rvm](https://rvm.io/){:target="_blank"}をインストールして利用します。

Rubyのプログラムは、テキストファイルでできています。Windowsのメモ帳でもかまいませんが、ソフトウェア開発には不向きです。プログラミングを支援するテキストエディタは有料無料を問わず多く存在します。また、その中でもプログラミングに特化した高機能エディタ（ソフトウェア）をIDE（Integrated Development Environment）と呼びます。

ここでは、Microsoftが提供しているプログラム開発環境[Visual Studio Code](https://azure.microsoft.com/ja-jp/products/visual-studio-code/){:target="_blank"}（無料）をインストールして使います。

## Rubyのインストール
ここでは、Windows10にRubyをインストールする方法を記載します。

### RubyInstaller for Windowsのインストール
ブラウザで[RubyInstaller for Windows](https://rubyinstaller.org/){:target="_blank"}を検索して表示します（リンクをクリックしても表示されます）。

<figure>
  <img src="{{ '/assets/images/ruby/03/rubyinstaller.png' | relative_url }}" alt="RubyInstaller for Windows">
</figure>

**Download**ボタンをクリックして、ダウンロード画面を表示します。

<figure>
  <img src="{{ '/assets/images/ruby/03/rubyinstaller-download.png' | relative_url }}" alt="RubyInstaller for Windows">
</figure>

画面には、**WITH DEVKIT**と**WITHOUT DEVKIT**とあります。通常は、**WITH DEVKIT**の方を使用します[^2]。

[^2]: DEVKITなしでもRubyは動作しますが、ライブラリを利用する場合に必要となる場合がありますので、DEVKITありをインストールした方が無難です。

複数のRubyバージョンと32ビット版（x86）か64ビット版（x64）が選べるようになっています。特に指定がなければ、右矢印（=>）のついたもの（ここでは**=> Ruby+Devkit 2.7.2-1 (x64)** ）を選択します。

2021年1月現在、DXRubyライブラリを利用する場合は、（64ビット版のパソコンでも）**Ruby+Devkit 2.6.6-2 (x86)**（バージョン2.6の32ビット版）を使用する必要があります。
{: .notice--info}

ダウンロードが終了したら、インストーラーを起動します。

<figure>
  <img src="{{ '/assets/images/ruby/03/rubyinstaller-install1.png' | relative_url }}" alt="RubyInstaller for Windows">
</figure>

**I accept the License**を選択して、**Next**ボタンをクリックします。

<figure>
  <img src="{{ '/assets/images/ruby/03/rubyinstaller-install2.png' | relative_url }}" alt="RubyInstaller for Windows">
</figure>

Rubyは、Cドライブ直下にインストールされます。必要がなければ変更せずに、**Install**ボタンをクリックします。

<figure>
  <img src="{{ '/assets/images/ruby/03/rubyinstaller-install3.png' | relative_url }}" alt="RubyInstaller for Windows">
</figure>

必要がなければ変更せずに、**Next**ボタンをクリックすると、インストールが開始されます。インストールが終了すると、次の画面が表示されます。

<figure>
  <img src="{{ '/assets/images/ruby/03/rubyinstaller-install4.png' | relative_url }}" alt="RubyInstaller for Windows">
</figure>

MSYS2をインストールするか決めることができます。[MSYS2](https://www.msys2.org/){:target="_blank"}は、Windows上でUnix系ツールを利用するためのアプリで、Rubyに提供されているライブラリをWindowsで使用できるようにします。特に問題がなければ、変更せずに**Finish**ボタンをクリックします。

### MSYS2のインストール
RubyInstaller for Windowsの画面が消えると、コマンドプロンプトの画面が起動します。

<figure>
  <img src="{{ '/assets/images/ruby/03/msys2-install1.png' | relative_url }}" alt="RubyInstaller for Windows">
</figure>

特に変更の必要がなければ、キーボードの**Enter**キーを押すと、インストールが開始されます。

<figure>
  <img src="{{ '/assets/images/ruby/03/msys2-install2.png' | relative_url }}" alt="RubyInstaller for Windows">
</figure>

インストールが終了すると、緑色で**succeeded**と表示され、最初に表示されていた内容が再度表示されます（[]内は空欄になっています）。キーボードの**Enter**キーを押すと、コマンドプロンプトが閉じ、インストールが終了します。

### Rubyの動作確認
Rubyがインストールできているかを確認します。

コマンドプロンプトを起動します。起動方法はいくつかありますが、Windows10の左下にある検索窓に**cmd**と入力する方法が簡単です。

<figure>
  <img src="{{ '/assets/images/ruby/03/ruby-confirm1.png' | relative_url }}" alt="Rubyの動作確認">
</figure>

コマンドプロンプトが検索できたら、**開く**をクリックして起動します。

<figure>
  <img src="{{ '/assets/images/ruby/03/ruby-confirm2.png' | relative_url }}" alt="Rubyの動作確認">
</figure>

コマンドプロンプトに`ruby -v`と入力して、**Enter**キーを押します。Rubyのバージョンが表示されれば、Rubyは正常にインストールされています。

## プログラム開発環境のインストール
ここでは、Windows10にVisual Studio Codeをインストールする方法を記載します。


### Visual Studio Codeのインストール
ブラウザで[Visual Studio Code](https://azure.microsoft.com/ja-jp/products/visual-studio-code/){:target="_blank"}を検索して表示します（リンクをクリックしても表示されます）。

<figure>
  <img src="{{ '/assets/images/ruby/03/visual-studio-code.png' | relative_url }}" alt="Visual Studio Code">
</figure>

**今すぐダウンロード**ボタンをクリックして、ダウンロード画面を表示します。

<figure>
  <img src="{{ '/assets/images/ruby/03/vscode-download.png' | relative_url }}" alt="Visual Studio Code">
</figure>

**User Installer**の**64 bit**をクリックします（管理者権限があればSystem Installerでも問題ありません）。

ダウンロードが終了したら、インストーラーを起動します。

<figure>
  <img src="{{ '/assets/images/ruby/03/vscode-install1.png' | relative_url }}" alt="Visual Studio Code">
</figure>

**同意する**を選択して、**次へ**ボタンをクリックします。

<figure>
  <img src="{{ '/assets/images/ruby/03/vscode-install2.png' | relative_url }}" alt="Visual Studio Code">
</figure>

インストール先に問題がなければ、変更せずに、**次へ**ボタンをクリックします。

<figure>
  <img src="{{ '/assets/images/ruby/03/vscode-install3.png' | relative_url }}" alt="Visual Studio Code">
</figure>

確認ダイアログが表示されますので、**はい**ボタンをクリックします。

<figure>
  <img src="{{ '/assets/images/ruby/03/vscode-install4.png' | relative_url }}" alt="Visual Studio Code">
</figure>

特に必要がなければ、変更せずに、**次へ**ボタンをクリックします。

<figure>
  <img src="{{ '/assets/images/ruby/03/vscode-install5.png' | relative_url }}" alt="Visual Studio Code">
</figure>

特に必要がなければ、変更せずに、**次へ**ボタンをクリックします。

<figure>
  <img src="{{ '/assets/images/ruby/03/vscode-install6.png' | relative_url }}" alt="Visual Studio Code">
</figure>

**インストール**ボタンをクリックすると、インストールが開始されます。インストールが終了すると、次の画面が表示されます。

<figure>
  <img src="{{ '/assets/images/ruby/03/vscode-install7.png' | relative_url }}" alt="Visual Studio Code">
</figure>

**完了**ボタンをクリックすると、Visual Studio Codeが起動します。

<figure>
  <img src="{{ '/assets/images/ruby/03/vscode-install8.png' | relative_url }}" alt="Visual Studio Code">
</figure>

### Visual Studio Codeの動作確認
Visual Studio Code（以下VSCode）からRubyが実行できるか確認します。

VSCodeのメニューより、**Terminal** => **New Terminal**をクリックします。

<figure>
  <img src="{{ '/assets/images/ruby/03/vscode-confirm1.png' | relative_url }}" alt="Visual Studio Code">
</figure>

VSCodeの画面下側にTerminal（コマンドプロンプト）が表示されます。

<figure>
  <img src="{{ '/assets/images/ruby/03/vscode-confirm2.png' | relative_url }}" alt="Visual Studio Code">
</figure>

Terminalに、
```bash
ruby -v
```
と入力して、**Enter**キーを押します。Rubyのバージョンが表示されれば、VSCodeでRubyが利用できます。

### Visual Studio Codeの日本語化
インストール直後のVSCodeは、言語が英語になっていますので、設定を変更して日本語化します。

VSCodeのメニューより、**View** => **Command Palette**をクリックします。

<figure>
  <img src="{{ '/assets/images/ruby/03/vscode-setting1.png' | relative_url }}" alt="Visual Studio Code">
</figure>

入力フォームが表示されます。

<figure>
  <img src="{{ '/assets/images/ruby/03/vscode-setting2.png' | relative_url }}" alt="Visual Studio Code">
</figure>

入力フォームに、`configure display loanguage`と入力します。入力途中でも、下側に候補が表示されますので、**Configure Display Language**をクリックします。

<figure>
  <img src="{{ '/assets/images/ruby/03/vscode-setting3.png' | relative_url }}" alt="Visual Studio Code">
</figure>

入力フォームの下側に表示される**Install additional language**をクリックします。

<figure>
  <img src="{{ '/assets/images/ruby/03/vscode-setting4.png' | relative_url }}" alt="Visual Studio Code">
</figure>

左側のサイドバーにインストール可能な言語の一覧が表示されますので、**日本語**の**Install**ボタンをクリックします。

<figure>
  <img src="{{ '/assets/images/ruby/03/vscode-setting5.png' | relative_url }}" alt="Visual Studio Code">
</figure>

インストールが開始されます。インストールが終了すると、右下側に再起動を促すメッセージが表示されますので、その中の**Restart Now**ボタンをクリックします。

<figure>
  <img src="{{ '/assets/images/ruby/03/vscode-setting6.png' | relative_url }}" alt="Visual Studio Code">
</figure>

VSCodeが再起動され、メニューなどが日本語になっていることを確認します。

<figure>
  <img src="{{ '/assets/images/ruby/03/vscode-setting7.png' | relative_url }}" alt="Visual Studio Code">
</figure>
