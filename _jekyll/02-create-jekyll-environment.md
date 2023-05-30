---
title: "Jekyllの実行環境構築"
permalink: /jekyll/create-jekyll-environment/
toc: true
---
## 事前準備
Jekyllを利用するには以下のアプリが必要となります。
- Ruby
  - バージョンは2.5.0以上（GitHub Pagesを利用してサイトを公開する場合は、指定のバージョンを使う[^1]）。特に指定がなければ最新版をインストールする。
  - Windowsの場合は、RubyInstaller for WindowsのWITH DEVKITをインストールする。
- テキストエディタ
  - 普段からプログラミングなどで利用しているテキストエディタでよい。
  - 特になければVisual Studio Code（無料）を推奨。

[^1]: GitHub PagesのDependency versions（[https://pages.github.com/versions/](https://pages.github.com/versions/){:target="_blank"}）を参照。

## Jekyllのインストール
ターミナル（Windowsの場合は、コマンドプロンプトまたはPowerShell）を開いて、以下のコマンドを実行します。
```bash
gem install jekyll
```
上記コマンドでは、Jekyllの最新バージョンがインストールされます。  
特定のバージョンをインストールする場合[^1]は、以下のコマンドを実行します。
```bash
gem install jekyll -v "特定のバージョン"
```
インストールが終了したらバージョンを確認します。
```bash
jekyll -v
jekyll 3.9.3
```
