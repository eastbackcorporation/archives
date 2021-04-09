---
title: "3Dプリントの実行"
permalink: /make3d/3d-printing/
toc: true
---
ここでは実際にKossel Mini EBで3Dプリントを行います。

以下が実際にプリントしている様子の映像です。

[![YouTube動画](https://img.youtube.com/vi/sJtYJfl0eDg/0.jpg)](https://www.youtube.com/watch?v=sJtYJfl0eDg "Kossel Mini EB")

「3Dモデルデータの取得」でダウンロードしたMarvinをプリントします。

Kossel Mini EB、PCの他にスティックのり、ピンセットを準備します。​Kossel Mini EBを電源に接続し、USBケーブルをPCに接続します。

<figure>
  <img src="{{ '/assets/images/make3d/502/502-1.webp' | relative_url }}" alt="502-1">
</figure>

最初に、スライサーを使用して、STL形式の3DモデルデータをGCodeに変換します。

Kisslicerを起動します。

<figure>
  <img src="{{ '/assets/images/make3d/502/502-2.webp' | relative_url }}" alt="502-2">
</figure>

画面右上の「Open」ボタンをクリックして、3Dモデルデータ「Marvin」のSTLファイルを選択します。画面の3D表示部分にプリントするMarvinが表示されます。

「Open」ボタン右側の「Slice」ボタンを押します。

<figure>
  <img src="{{ '/assets/images/make3d/502/502-3.webp' | relative_url }}" alt="502-3">
</figure>

「Slice」ボタンが「Save」ボタンに変わりますので、「Save」ボタンを押してGCodeファイルを保存します。

<figure>
  <img src="{{ '/assets/images/make3d/502/502-4.webp' | relative_url }}" alt="502-4">
</figure>

これから作成したGCodeファイルを使用して3Dプリントを行いますが、その前にKossel Mini EBのベッドの中央にスティックのりを使ってのりを付けておきます。

PLA素材はガラス面に接着しますが、接着後素材が冷却され僅かに縮小するため、その密着強度は高くありません。

※ベッドを加熱すれば接着強度は増します。

そのため、何らかの方法で接着力を上げる必要があります。ここではスティックのりを使います。今回使用するスティックのりは比較的粘着力が低いものを使用していますが、接着しなかったり途中で外れてしまう場合は強力のりを試してみてください。

※最初の一層目の接着はベッドとノズル先端の距離に対して非常にシビアに依存します。このスティックのりは、そのバッファとしての役割も持っています。

<figure>
  <img src="{{ '/assets/images/make3d/502/502-5.webp' | relative_url }}" alt="502-5">
</figure>

Kossel Mini EBには２種類のプリント方法があります。１つ目はコントローラーを使う方法方法、２つ目はSDカードを使う方法です。最初にコントローラーを使ってプリントを行います。

Pronterfaceを起動し、「Connect」ボタンを押してKossel Mini EBに接続します。

<figure>
  <img src="{{ '/assets/images/make3d/502/502-6.webp' | relative_url }}" alt="502-6">
</figure>

画面右上の「Load file」ボタンを押して、MarvinのGCodeファイルを選択します。画面中央右側の3D表示部にMarvinの3Dモデルが表示されます。

<figure>
  <img src="{{ '/assets/images/make3d/502/502-7.webp' | relative_url }}" alt="502-7">
</figure>

画面右上の「Print」ボタンを押すと、プリントが開始されます。スライサーの設定にもよりますが、最初にキャリブレーションを行い、その後ヒーターの温度が上がります。指定した温度に達するとプリントが始まります。

<figure>
  <img src="{{ '/assets/images/make3d/502/502-8.webp' | relative_url }}" alt="502-8">
</figure>

<figure>
  <img src="{{ '/assets/images/make3d/502/502-9.webp' | relative_url }}" alt="502-9">
</figure>

<figure>
  <img src="{{ '/assets/images/make3d/502/502-10.webp' | relative_url }}" alt="502-10">
</figure>

注意：電源を切る（電源を抜く）場合は、ホットエンドの温度が室温近くまで下がっている事を必ず確認して下さい。ホットエンドが高温のまま電源を切ると、ホットエンドファンも切れるため、チューブが溶けてノズルが詰まってしまう場合があります。
{: .notice--warning}

次に、SDカードを使って3Dプリントを実行します。

コントローラーを使った3Dプリントでも同じですが、プリントを開始する前にホットエンドを加熱しておく方が効率的です。LCDパネル右側にあるツマミを押します。下の写真の様な画面が表示されます。

<figure>
  <img src="{{ '/assets/images/make3d/502/502-11.webp' | relative_url }}" alt="502-11">
</figure>

ツマミを回すと画面左端にカーソルが動きますので、２番目の「Prepare」にカーソルを動かし、ツマミを押します。下の写真の様な画面が表示されます。

<figure>
  <img src="{{ '/assets/images/make3d/502/502-12.webp' | relative_url }}" alt="502-12">
</figure>

ツマミを回して４番目の「Preheat PLA」にカーソルを動かし、ツマミを押します。ヒーターへの加熱が始まりますので、１番目の「Main」にカーソルを移動させツマミを押します。前の画面に戻りますので、１番目の「Info screen」でツマミを押して最初の画面に戻ります。画面左上のヒーター温度を見ると、スラッシュの右側に「200℃」と表示されている事を確認します。

<figure>
  <img src="{{ '/assets/images/make3d/502/502-13.webp' | relative_url }}" alt="502-13">
</figure>

次にSDカードを準備します。SDカードの中にMarvinのGCodeファイルを保存します。フォルダを作成して中に入れても構いません。LCDパネル左側のスロットに（オモテウラ逆に）SDカードを挿入します。

<figure>
  <img src="{{ '/assets/images/make3d/502/502-14.webp' | relative_url }}" alt="502-14">
</figure>

ここで、すぐにプリントを実行しても問題ありませんが、プリント開始直後すぐに素材が出てこない場合があるため、手動でフィラメントをフィードしてみます。ヒーター温度が200℃に近い事を確認して、エクストルーダーハンドルを時計回りにゆっくり回します。しばらく回すとノズル先端から素材が出てくる事を確認します。

<figure>
  <img src="{{ '/assets/images/make3d/502/502-15.webp' | relative_url }}" alt="502-15">
</figure>

それでは、プリントを実行します。LCDパネル右側のツマミを押します。下の写真の様な画面が表示されます。

<figure>
  <img src="{{ '/assets/images/make3d/502/502-16.webp' | relative_url }}" alt="502-16">
</figure>

ツマミを回して４番目の「Print from SD」にカーソルを動かし、ツマミを押します。下の写真の様な画面が表示されます。

<figure>
  <img src="{{ '/assets/images/make3d/502/502-17.webp' | relative_url }}" alt="502-17">
</figure>

ツマミを回してMarvinのGCodeファイルを選択してツマミを押すと、プリントが開始されます。コントローラーから実行した時と同様、キャリブレーションが始まり、終了後3Dモデルのプリントが開始されます。

<figure>
  <img src="{{ '/assets/images/make3d/502/502-18.webp' | relative_url }}" alt="502-18">
</figure>

<figure>
  <img src="{{ '/assets/images/make3d/502/502-19.webp' | relative_url }}" alt="502-19">
</figure>

注意：電源を切る（電源を抜く）場合は、ホットエンドの温度が室温近くまで下がっている事を必ず確認して下さい。ホットエンドが高温のまま電源を切ると、ホットエンドファンも切れるため、チューブが溶けてノズルが詰まってしまう場合があります。
{: .notice--warning}
