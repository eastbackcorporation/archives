---
title: "DXRubyの実行環境構築"
permalink: /dxruby/create-dxruby-environment/
toc: true
---

{% include ruby_env.html %}

## Rubyの実行環境
DXRubyライブラリを実行するには、WindowsパソコンにRubyをインストールする必要があります。

[Rubyの実行環境構築](/archives/ruby/create-ruby-environment/){:target="_blank"}を参考に、Rubyをインストールしてください。

## DXRubyのインストール
DXRubyのインストールを行います。
DXRubyは[RubyGems](https://rubygems.org/){:target="_blank"}で管理されているため、簡単にインストールすることができます。

コマンドプロンプトにて、以下を実行します。

```bash
gem install dxruby
```

Windows10は、デフォルトでDirectXがインストールされていないため、DXRubyライブラリを実行（インクルード）するとエラーが発生します[^1]。  
DirectXをインストールするか、DirectXのDLLファイルを、rubyの実行ファイルと同じフォルダ（`bin`フォルダ）に置いてください。  
以下からDLLファイルをダウンロードできるようにしています。  
[Ruby(64bit版)用DLL](https://download.eastback.co.jp/directx/x64/d3dx9_40.dll){:target="_blank"}  
[Ruby(32bit版)用DLL](https://download.eastback.co.jp/directx/x86/d3dx9_40.dll){:target="_blank"}
{: .notice--warning}

[^1]: [Windows10では、DXRubyを動かすのに d3dx9_40.dllが必要](https://github.com/mirichi/dxruby/issues/3){:target="_blank"}
