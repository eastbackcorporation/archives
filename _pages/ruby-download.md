---
title: "Ruby実行環境のダウンロード"
permalink: /ruby-download/
---
**Rubyの実行環境（Windows版、DXRubyインストール済み）をzipで提供しています。**

下記ボタンをクリックするとダウンロードが始まります。

[<i class="fas fa-download"></i> Ruby実行環境のダウンロード](https://download.eastback.co.jp/ruby/ruby_lecture.zip){: .btn .btn--success}

## 内容
- Ruby: RubyInstaller for Windows Ruby 3.0.4-1 (x86) (Without Devkit) （DXRuby 1.4.7 インストール済み、DirectX DLLを含む）
- IDE: Visual Studio Code 1.67.2 （.zip 64bit版）

[2022/06/09] RubyとVSCodeのバージョンをアップしました。  
ターミナルに、Rubyが使用できるPowerShellを追加しました。
{: .notice--info} 

[2021/01/19] RubyInstaller 64ビット(x64)版では、DXRubyでwavファイルを再生するとエラーが発生します[^1]。そのため32ビット(x86)版を使用しています。
{: .notice--warning} 

[^1]: [[DXRuby 1.4.7] 64bitでは、Sound.newでエラー](https://github.com/mirichi/dxruby/issues/4){:target="_blank"}

## 利用方法
ダウンロードした**ruby_lecture.zip**を、Cドライブ直下に展開してください。

エクスプローラーで**C:¥ruby_lecture¥code.bat**をダブルクリックすると、Visual Studio Codeが起動します。

作業フォルダは、 **C:¥ruby_lecture¥code**に設定してあります。

ターミナルのデフォルトは、**【Ruby】Command Prompt**です。Rubyのパスを通してありますので、Rubyが使用できます。また、**【Ruby】PowerShell**は、PowerShellでRubyが使用できます。

## 注意
初回起動時に、**Microsoft Defender SmartScreen**のダイアログが表示されることがあります。

**詳細情報**をクリックしてください。

<figure>
  <img src="{{ '/assets/images/ruby/download/dialog1.png' | relative_url }}" alt="Microsoft Defender SmartScreen">
</figure>

下側に**実行**ボタンが表示されますので、クリックするとVisual Studio Codeが起動します。

<figure>
  <img src="{{ '/assets/images/ruby/download/dialog2.png' | relative_url }}" alt="Microsoft Defender SmartScreen">
</figure>
