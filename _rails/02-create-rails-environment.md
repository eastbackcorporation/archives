---
title: "Railsアプリ開発環境の構築"
permalink: /rails/create-rails-environment/
toc: true
---
## ローカル環境の構築
### Rubyの実行環境
Railsアプリを開発するには、Rubyをインストールする必要があります。

[Rubyの実行環境構築](/archives/ruby/create-ruby-environment/){:target="_blank"}を参考に、Rubyをインストールしてください。

### Railsのインストール
Railsは、[RubyGems](https://rubygems.org/){:target="_blank"}で管理されているため、簡単にインストールすることができます。

コマンドプロンプトで、以下を実行します。

```bash
gem install rails
```

多数の依存ライブラリをインストールするため、インストール完了までに、しばらく時間がかかる場合があります。

Rails6以降は、Railsの他に[Node.js](https://nodejs.org/ja/){:target="_blank"}、[yarn](https://yarnpkg.com/){:target="_blank"}を別途インストールする必要があります。
{: .notice--warning} 


## クラウド環境の構築
### Paiza Cloud
近年、ウェブでプログラム開発環境を提供するサービスが多く出てきました。

ここでは、無料で使うことができる[Paiza Cloud](https://paiza.cloud/ja/){:target="_blank"}を使う手順を記載します。

ブラウザから、[Paiza Cloud](https://paiza.cloud/ja/){:target="_blank"}にアクセスします。

<figure>
  <img src="{{ '/assets/images/rails/02/paiza.png' | relative_url }}" alt="Paiza Cloud">
</figure>

既にアカウントを持っている場合は、**ログイン**ボタンを押してください。初めての場合は、**登録無料**ボタンを押してください。

#### アカウントを持ってない場合

**登録無料**ボタンを押します。

<figure>
  <img src="{{ '/assets/images/rails/02/paiza2.png' | relative_url }}" alt="Paiza Cloud">
</figure>

**アカウント作成**ダイアログが表示されるので、**メールアドレス**、**ユーザ名**、**パスワード**を入力します。**私はロボットではありません**のチェックボックスをチェックして、**アカウント作成**ボタンを押します。

もし、**GitHub**、**Facebook**、**Google+**のアカウントを持っていれば、下のボタンを押すと手間が省けます。
{: .notice--info} 

<figure>
  <img src="{{ '/assets/images/rails/02/paiza3.png' | relative_url }}" alt="Paiza Cloud">
</figure>

**確認メールを・・・に送信しました。メールに書かれたURLをクリックしてください。**と表示されますので、指示通りにメールを開いて、URLをクリックします。

<figure>
  <img src="{{ '/assets/images/rails/02/paiza4.png' | relative_url }}" alt="Paiza Cloud">
</figure>

ブラウザのタブ（またはウィンドウ）が開き、Paiza Cloudにログインした状態になります。

#### アカウントを持っている場合

**ログイン**ボタンを押します。

<figure>
  <img src="{{ '/assets/images/rails/02/paiza5.png' | relative_url }}" alt="Paiza Cloud">
</figure>

**ログイン**ダイアログが表示されるので、**メールアドレス**、**パスワード**を入力します。**ログイン**ボタンを押します。

もし、**GitHub**、**Facebook**、**Google+**のアカウントを使って、Paiza Cloudのアカウントを作成されている場合は、該当するボタンを押してください。
{: .notice--info} 

<figure>
  <img src="{{ '/assets/images/rails/02/paiza4.png' | relative_url }}" alt="Paiza Cloud">
</figure>

ブラウザのタブ（またはウィンドウ）が開き、Paiza Cloudにログインした状態になります。
