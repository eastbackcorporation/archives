---
title: "マージとプルリクエスト"
permalink: /github/merge-and-pull-request/
toc: true
---
## マージとは

ブランチを統合することを、マージ（merge）といいます。

イメージ的には、「main」ブランチから派生させて作成した開発用ブランチ「add-new-functions」(例)で開発を行い、問題ないことを確認した後、「add-new-functions」ブランチを「main」ブランチにマージします。マージでは、「add-new-functions」の変更分が「main」に取り込まれます。

実際には、木の幹と枝のように、いろいろなタイミングで、複数のブランチが作成されるのが普通です。ブランチが複数になればなるほど、マージは複雑になります。マージが適切に行われないと、本体（「main」ブランチ）を壊してしまうことにもなりかねません。

それほど、マージは重要で慎重に行うべきものです。

## プルリクエストとは

プルリクエスト（pull request）は、GitHubが持っている機能の一つです。

「自分の開発した機能を取り込んでください。」「バグを見つけました。修正しましたので、取り込んでください。」といった、依頼を行うことができます。

マージのできる権限を持った担当者は、プルリクエストの内容を確認・検証して、再修正を依頼したり、問題なければマージすることができます。

マージは煩雑で責任の伴う作業です。プルリクエストを使うことで、半自動的なマージのチェック（コンフリクトのチェック）や体系立った処理が可能となり、担当者の負担が軽減します。

※ システムやツールを使わず、手作業で行うマージ作業を「ハンドマージ」と言ったりしますが、これは大変な作業です。

## プルリクエストとマージの実行

### プルリクエストの作成

「ブランチ操作」で作成した、「test1」ブランチのプルリクエストを作成します。

GitHubのリポジトリのページを表示します。

プルリクエストを作成を促す表示が出ている場合があります。これは、新規ブランチがpushされたり、「main」ブランチ以外のブランチが更新されると表示されます。

表示されている「Compare & ull request」ボタンをクリックしても作成できますが、ここでは、正規の手順でプルリクエストを作成します。

<figure>
  <img src="{{ '/assets/images/github/06/pull-request1.png' | relative_url }}" alt="GitHub Login" class="img_border">
</figure>

「2 branches」をクリックして、ブランチの一覧を表示します。

<figure>
  <img src="{{ '/assets/images/github/06/pull-request2.png' | relative_url }}" alt="GitHub Login" class="img_border">
</figure>

ブランチの一覧から、マージしてほしいブランチ（ここでは「test1」）の右側にある「New pull request」ボタンを押します。

<figure>
  <img src="{{ '/assets/images/github/06/pull-request3.png' | relative_url }}" alt="GitHub Login" class="img_border">
</figure>

「Open a pull request」画面が表示されます。

最初に、どのブランチにどのブランチをマージするかを確認します。ここでは「main」ブランチに「test1」ブランチをマージします。

プルリクエストのタイトルを入力します。デフォルトでコミットメッセージが入力されています。

その他、注意事項などがあれば記入します。添付ファイルも可能です。

設定が終わったら、「Create pull request」ボタンを押します。

<figure>
  <img src="{{ '/assets/images/github/06/pull-request4.png' | relative_url }}" alt="GitHub Login" class="img_border">
</figure>

作成したプルリクエストが表示されます。マージのチェックは自動的に行われます。問題がなければ、「This branch has no conflicts with the base branch」と表示されます。もし問題があれば表示されます。

ここでチェックされるのは、主にコンフリクト（衝突）です。コンフリクトとは、例えば、既に書き換わっている箇所を書き換えようとするときに発生します。どちらの変更を採用するかは、自動的に判断できないため、マージ担当者が判断することになります。

マージ担当者は、ここでは自分自身なので、「Merge pull request」ボタンが押せるようになっています。

<figure>
  <img src="{{ '/assets/images/github/06/pull-request5.png' | relative_url }}" alt="GitHub Login" class="img_border">
</figure>

### マージの実行

問題ない（コンフリクトがない）ことを確認し、「Merge pull request」ボタンを押します。

<figure>
  <img src="{{ '/assets/images/github/06/pull-request6.png' | relative_url }}" alt="GitHub Login" class="img_border">
</figure>

「Confirm merge」ボタンが表示されますので、このボタンを押します。

<figure>
  <img src="{{ '/assets/images/github/07/pull-request7.png' | relative_url }}" alt="GitHub Login" class="img_border">
</figure>

これでマージは完了です。左上の「Code」をクリックします。

<figure>
  <img src="{{ '/assets/images/github/07/pull-request8.png' | relative_url }}" alt="GitHub Login" class="img_border">
</figure>

「main」ブランチに「test1」ブランチの内容が反映されています。

「2 branches」をクリックして、ブランチの一覧を表示します。

<figure>
  <img src="{{ '/assets/images/github/07/pull-request9.png' | relative_url }}" alt="GitHub Login" class="img_border">
</figure>

「test1」ブランチには「merged」と表示されています。「test1」ブランチは正常に取り込まれたので、削除しても構いません。

<figure>
  <img src="{{ '/assets/images/github/07/pull-request10.png' | relative_url }}" alt="GitHub Login" class="img_border">
</figure>
