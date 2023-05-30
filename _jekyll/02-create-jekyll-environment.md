---
title: "Jekyllの実行環境構築"
permalink: /jekyll/create-jekyll-environment/
toc: true
---
## 事前準備
Jekyllを利用するには以下のアプリが必要となります。
- Ruby
  - バージョンは2.5.0以上（GitHub Pagesを利用してサイトを公開する場合は、指定のバージョンを使う[^1]<sup>,</sup>[^2]）。特に指定がなければ最新版をインストールする。
  - Windowsの場合は、RubyInstaller for WindowsのWITH DEVKITをインストールする。
- テキストエディタ
  - 普段からプログラミングなどで利用しているテキストエディタでよい。
  - 特になければVisual Studio Code（無料）を推奨。

[^1]: GitHub Pagesで利用できるバージョン一覧（Dependency versions）: [https://pages.github.com/versions/](https://pages.github.com/versions/){:target="_blank"}

[^2]: GitHub Actionsを利用すれば、バージョンの制限は受けない: [https://jekyllrb.com/docs/continuous-integration/github-actions/](https://jekyllrb.com/docs/continuous-integration/github-actions/){:target="_blank"}

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
