---
title: "GitおよびGitHubの概要"
permalink: /github/about-github/
toc: true
---
## Gitとは

Git（ギット）は、プログラムのソースコードなどの変更履歴を記録・追跡するための分散型バージョン管理システムです。

Linuxカーネルのソースコード管理に用いるためにリーナス・トーバルズ[^1]によって開発されました。

[^1]: リーナス・トーバルズはLinuxの開発者

Gitでは、各ユーザのワーキングディレクトリに、全履歴を含んだリポジトリの完全な複製が作られます。

したがって、ネットワークにアクセスできないなどの理由で中心リポジトリにアクセスできない環境でも、履歴の調査や変更の記録といったほとんどの作業を行うことができます。

これが「分散型」と呼ばれる理由です。[^2]

[^2]: [Wikiペディア - Git](https://ja.wikipedia.org/wiki/Git){:target="_blank"}

<figure>
  <img src="{{ '/assets/images/github/01/distributed.png' | relative_url }}" alt="Git" class="img_border">
</figure>


## GitHubとは

GitHub（ギットハブ）は、ソフトウェア開発プロジェクトのための共有ウェブサービスであり、Gitバージョン管理システムを使用しています。

Ruby on RailsおよびErlangで記述されており、GitHub社によって保守されています（GitHub社は、2018年10月にMicrosoft社によって買収された）。

GitHubは、個人向けの無料プランと、小規模プロジェクトおよび大規模プロジェクト（企業）向けの有料プランを提供しています。

2009年のユーザー調査によると、GitHubは最もポピュラーなGitホスティングサイトとなりました。[^3]

[^3]: [Wikiペディア - GitHub](https://ja.wikipedia.org/wiki/GitHub){:target="_blank"}

## リファレンス

Git公式ウェブサイト
[https://git-scm.com/](https://git-scm.com/){:target="_blank"}

Gitドキュメント
[https://git-scm.com/doc/](https://git-scm.com/doc/){:target="_blank"}

GitHub公式ウェブサイト
[https://github.com/](https://github.com/){:target="_blank"}

GitHubドキュメント
[https://docs.github.com/ja/](https://docs.github.com/ja/){:target="_blank"}
