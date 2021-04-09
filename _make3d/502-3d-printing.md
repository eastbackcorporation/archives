---
title: "3Dプリントの実行"
permalink: /make3d/3d-printing/
toc: true
---
ここでは実際にKossel Mini EBで3Dプリントを行います。

以下が実際にプリントしている様子の映像です。

「3Dモデルデータの取得」でダウンロードしたMarvinをプリントします。

Kossel Mini EB、PCの他にスティックのり、ピンセットを準備します。​Kossel Mini EBを電源に接続し、USBケーブルをPCに接続します。

最初に、スライサーを使用して、STL形式の3DモデルデータをGCodeに変換します。
Kisslicerを起動します。

画面右上の「Open」ボタンをクリックして、3Dモデルデータ「Marvin」のSTLファイルを選択します。画面の3D表示部分にプリントするMarvinが表示されます。

「Open」ボタン右側の「Slice」ボタンを押します。

「Slice」ボタンが「Save」ボタンに変わりますので、「Save」ボタンを押してGCodeファイルを保存します。

これから作成したGCodeファイルを使用して3Dプリントを行いますが、その前にKossel Mini EBのベッドの中央にスティックのりを使ってのりを付けておきます。

PLA素材はガラス面に接着しますが、接着後素材が冷却され僅かに縮小するため、その密着強度は高くありません。
※ベッドを加熱すれば接着強度は増します。

そのため、何らかの方法で接着力を上げる必要があります。ここではスティックのりを使います。今回使用するスティックのりは比較的粘着力が低いものを使用していますが、接着しなかったり途中で外れてしまう場合は強力のりを試してみてください。
※最初の一層目の接着はベッドとノズル先端の距離に対して非常にシビアに依存します。このスティックのりは、そのバッファとしての役割も持っています。

Kossel Mini EBには２種類のプリント方法があります。１つ目はコントローラーを使う方法方法、２つ目はSDカードを使う方法です。最初にコントローラーを使ってプリントを行います。

Pronterfaceを起動し、「Connect」ボタンを押してKossel Mini EBに接続します。

画面右上の「Load file」ボタンを押して、MarvinのGCodeファイルを選択します。画面中央右側の3D表示部にMarvinの3Dモデルが表示されます。

画面右上の「Print」ボタンを押すと、プリントが開始されます。スライサーの設定にもよりますが、最初にキャリブレーションを行い、その後ヒーターの温度が上がります。指定した温度に達するとプリントが始まります。

注：電源を切る（電源を抜く）場合は、ホットエンドの温度が室温近くまで下がっている事を必ず確認して下さい。ホットエンドが高温のまま電源を切ると、ホットエンドファンも切れるため、チューブが溶けてノズルが詰まってしまう場合があります。

次に、SDカードを使って3Dプリントを実行します。

コントローラーを使った3Dプリントでも同じですが、プリントを開始する前にホットエンドを加熱しておく方が効率的です。LCDパネル右側にあるツマミを押します。下の写真の様な画面が表示されます。

ツマミを回すと画面左端にカーソルが動きますので、２番目の「Prepare」にカーソルを動かし、ツマミを押します。下の写真の様な画面が表示されます。

ツマミを回して４番目の「Preheat PLA」にカーソルを動かし、ツマミを押します。ヒーターへの加熱が始まりますので、１番目の「Main」にカーソルを移動させツマミを押します。前の画面に戻りますので、１番目の「Info screen」でツマミを押して最初の画面に戻ります。画面左上のヒーター温度を見ると、スラッシュの右側に「200℃」と表示されている事を確認します。

次にSDカードを準備します。SDカードの中にMarvinのGCodeファイルを保存します。フォルダを作成して中に入れても構いません。LCDパネル左側のスロットに（オモテウラ逆に）SDカードを挿入します。

ここで、すぐにプリントを実行しても問題ありませんが、プリント開始直後すぐに素材が出てこない場合があるため、手動でフィラメントをフィードしてみます。ヒーター温度が200℃に近い事を確認して、エクストルーダーハンドルを時計回りにゆっくり回します。しばらく回すとノズル先端から素材が出てくる事を確認します。

それでは、プリントを実行します。LCDパネル右側のツマミを押します。下の写真の様な画面が表示されます。

ツマミを回して４番目の「Print from SD」にカーソルを動かし、ツマミを押します。下の写真の様な画面が表示されます。

ツマミを回してMarvinのGCodeファイルを選択してツマミを押すと、プリントが開始されます。コントローラーから実行した時と同様、キャリブレーションが始まり、終了後3Dモデルのプリントが開始されます。

注：電源を切る（電源を抜く）場合は、ホットエンドの温度が室温近くまで下がっている事を必ず確認して下さい。ホットエンドが高温のまま電源を切ると、ホットエンドファンも切れるため、チューブが溶けてノズルが詰まってしまう場合があります。