---
title: "DXRubyの実行環境構築"
permalink: /dxruby/create-dxruby-environment/
toc: true
---

{% include ruby_env.html %}

## Rubyの実行環境
DXRubyライブラリを実行するには、WindowsパソコンにRubyをインストールする必要があります。

[Rubyの実行環境構築](/archives/ruby/create-ruby-environment/){:target="_blank"}を参考に、Rubyをインストールしてください。

[2022/06/09] DXRubyライブラリを利用する場合は、64ビットのWindowsパソコンでも、**RubyInstaller 32ビット(x86)版**を使用する必要があります。  
また、DXRubyライブラリは、Ruby3.1系では利用できませんので、Ruby3.0系以降をご使用ください。
{: .notice--warning}

[2020/01/19] **RubyInstaller 64bit(x64)版**では、DXRubyでwavファイルを再生するとエラーが発生します[^1]。そのため、**RubyInstaller 32bit(x86)版**をインストールしてください。
{: .notice--warning} 

[^1]: [[DXRuby 1.4.7] 64bitでは、Sound.newでエラー](https://github.com/mirichi/dxruby/issues/4){:target="_blank"}

## DXRubyのインストール
DXRubyのインストールを行います。
DXRubyは[RubyGems](https://rubygems.org/){:target="_blank"}で管理されているため、簡単にインストールすることができます。

コマンドプロンプトにて、以下を実行します。

```bash
gem install dxruby
```

Windows10は、デフォルトでDirectXがインストールされていないため、DXRubyライブラリを実行（インクルード）するとエラーが発生します[^2]。  
DirectXをインストールするか、DirectXのDLLファイルを、rubyの実行ファイルと同じフォルダ（`bin`フォルダ）に置いてください。  
以下からDLLファイルをダウンロードできるようにしています。  
[RubyInstaller 32bit(x86)版用DLLファイル: d3dx9_40.dll](https://download.eastback.co.jp/directx/x86/d3dx9_40.dll){:target="_blank"}  
64ビット版のRubyInstallerをご使用の場合は、以下からダウンロードしてください（64ビット版はエラーが発生するのでお勧めしません）。  
[RubyInstaller 64bit(x64)版用DLLファイル: d3dx9_40.dll](https://download.eastback.co.jp/directx/x64/d3dx9_40.dll){:target="_blank"}  
上記DLLを含むランタイムのインストーラーが必要な場合は、以下からダウンロードしてください。  
[DirectX End-User Runtimes(June 2010)ファイル: directx_Jun2010_redist.exe](https://download.eastback.co.jp/directx/directx_Jun2010_redist.exe){:target="_blank"}
{: .notice--warning}

[^2]: [Windows10では、DXRubyを動かすのに d3dx9_40.dllが必要](https://github.com/mirichi/dxruby/issues/3){:target="_blank"}
