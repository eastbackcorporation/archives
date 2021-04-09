---
title: "ヒートベッドの取り付け"
permalink: /make3d/installation-of-heat-bed/
toc: true
---
【アクセサリーとして発売している「ヒートベッドセット」を購入された方のためのマニュアルです。】
{: .notice--info} 

ヒートベッドを使用することにより、プリント中の造形物とベッドの温度差を小さくできます。これにより、造形物の反りやプリント中ベッドから剥がれてしまう失敗を抑えることができます。

また、ABS素材など熱膨張率の大きな素材のプリントが可能となります。

ヒートベッドを使用するためには、「ヒートベッドセット」の他、「**電源**」が別途必要になります。Arduino、モーター、ホットエンドなどは、ACアダプターにより12V5Aを供給することで動作していますが、それとは別にヒートベッド用として12V11Aが必要となります。

ここでは、デスクトップPCで使用されるATX用電源を加工して、12V5Aと12V11Aの両方を供給する方法を示します。

以下のものを準備します。

- ヒートベッドセット
- ATX電源

<figure>
  <img src="{{ '/assets/images/make3d/601/601-1.webp' | relative_url }}" alt="601-1">
</figure>

<figure>
  <img src="{{ '/assets/images/make3d/601/601-2.webp' | relative_url }}" alt="601-2">
</figure>

最初にATX電源を加工します。

「ATX12V 4ピンコネクタ」を見つけます。これはCPUに電力を供給するために使用されるもので、黄色２本と黒２本のケーブルで構成されています。大電力が必要とされるPC用では８ピンの場合があります。その場合も黄色２本、黒２本の４本のみ使用します。

注意：「ATX12V 4ピンコネクタ」が、12V5Aと12V11A（合計16A）供給できる事を事前に確認してください。もし16Aに満たない場合は、別のケーブル（例えば「PCI Express電源コネクタ」を併用するか、付属のACアダプターを併用する必要があります。
{: .notice--warning}

<figure>
  <img src="{{ '/assets/images/make3d/601/601-3.webp' | relative_url }}" alt="601-3">
</figure>

ニッパーでコネクタを切断します。

<figure>
  <img src="{{ '/assets/images/make3d/601/601-4.webp' | relative_url }}" alt="601-4">
</figure>

<figure>
  <img src="{{ '/assets/images/make3d/601/601-5.webp' | relative_url }}" alt="601-5">
</figure>

ストリッパーなどで被覆を剥がします。

<figure>
  <img src="{{ '/assets/images/make3d/601/601-6.webp' | relative_url }}" alt="601-6">
</figure>

次に「PCメイン電源コネクタ」を見つけます。２０ピンまたは２４ピンのコネクタです。下図で持ち上げている黒と緑のケーブルを使用します。これは通常電源スイッチに使われるケーブルで緑ケーブルを短絡させることで、スイッチがONの状態になります。

<figure>
  <img src="{{ '/assets/images/make3d/601/601-7.webp' | relative_url }}" alt="601-7">
</figure>

次にクリップを１個準備します。ニッパーで切断し、U字型の部分を作ります。

<figure>
  <img src="{{ '/assets/images/make3d/601/601-8.webp' | relative_url }}" alt="601-8">
</figure>

<figure>
  <img src="{{ '/assets/images/make3d/601/601-9.webp' | relative_url }}" alt="601-9">
</figure>

下図のように、黒と緑のケーブルをブリッジさせるように、コネクタにクリップを差し込みます。

これにより、ATX電源から電力を供給できるようになります。クリップでの接続は一時的なものなので、継続的に使用する場合は、これらのケーブルを切断してハンダ付けなどをするか、スイッチに接続するなどの対応をお勧めします

<figure>
  <img src="{{ '/assets/images/make3d/601/601-10.webp' | relative_url }}" alt="601-10">
</figure>

黄色２本、黒２本以外のケーブルは結束バンドなどで止めます。

<figure>
  <img src="{{ '/assets/images/make3d/601/601-11.webp' | relative_url }}" alt="601-11">
</figure>

次に、ヒートベッドセットからヒートベッドとコルク円盤を取り出します（ヒートベッド裏面中央にはサーミスタがハンダ付けされています）。

<figure>
  <img src="{{ '/assets/images/make3d/601/601-12.webp' | relative_url }}" alt="601-12">
</figure>

コルク円盤の両面テープの剥離紙を剥がします。コルク円盤をヒートベッドの裏面に貼り付けます。

<figure>
  <img src="{{ '/assets/images/make3d/601/601-13.webp' | relative_url }}" alt="601-13">
</figure>

<figure>
  <img src="{{ '/assets/images/make3d/601/601-14.webp' | relative_url }}" alt="601-14">
</figure>

次に、Kossel Mini EB本体を準備します。既存のガラスタブ３個とベッド（ガラス）を外します。

<figure>
  <img src="{{ '/assets/images/make3d/601/601-15.webp' | relative_url }}" alt="601-15">
</figure>

LCDマウントのボルトを１箇所外します。外した側のアルミフレームの端からM3ナットを入れます。LCDマウントのナットを中央に寄せ、新しく入れたナットを用いて、LCDマウントのボルトを再び締めます。

<figure>
  <img src="{{ '/assets/images/make3d/601/601-16.webp' | relative_url }}" alt="601-16">
</figure>

<figure>
  <img src="{{ '/assets/images/make3d/601/601-17.webp' | relative_url }}" alt="601-17">
</figure>

他のアルミフレームについても端からナットを入れて、それぞれ２個のナットがアルミフレームの中央付近にくるようにします。

<figure>
  <img src="{{ '/assets/images/make3d/601/601-18.webp' | relative_url }}" alt="601-18">
</figure>

ヒートベッドをボトムボディーの中央に置きます。リトラクタが邪魔になるので、ボルトを緩めて奥の方へ移動させます。

<figure>
  <img src="{{ '/assets/images/make3d/601/601-19.webp' | relative_url }}" alt="601-19">
</figure>

<figure>
  <img src="{{ '/assets/images/make3d/601/601-20.webp' | relative_url }}" alt="601-20">
</figure>

ヒートベッドを奥のアルミフレーム（Z軸）に立て掛けます。サーミスタ用ケーブル（白）が上部へくるようにします。

<figure>
  <img src="{{ '/assets/images/make3d/601/601-21.webp' | relative_url }}" alt="601-21">
</figure>

サーミスタ用ケーブル（白）を下図のように、T1へ差し込みます。極性はありません。

<figure>
  <img src="{{ '/assets/images/make3d/601/601-22.webp' | relative_url }}" alt="601-22">
</figure>

<figure>
  <img src="{{ '/assets/images/make3d/601/601-23.webp' | relative_url }}" alt="601-23">
</figure>

ヒーターケーブル（赤）を下図のように、D8へ差し込み締めます。極性はありません。

<figure>
  <img src="{{ '/assets/images/make3d/601/601-24.webp' | relative_url }}" alt="601-24">
</figure>

電源ジャックを取り外し、下図のようにATX電源からの黄色と黒のケーブルを緑色のコネクタに差し込み締めます。

※緑色のコネクタの上部２つがヒートベッドで使用する12V11Aの端子で、下部２つがそれ以外で使用する12V5Aの端子です。極性は、それぞれ上側がプラス、下側がマイナスとなります。

※ACアダプターと併用する場合は、黄色、黒それぞれ２本の芯線を撚り、電源ジャックを残したまま、空いているコネクタに差し込みます。

<figure>
  <img src="{{ '/assets/images/make3d/601/601-25.webp' | relative_url }}" alt="601-25">
</figure>

下図のようにヒートベッドホルダーとガラスホルダーを組み合わせて、M3-20ボルトを通します。同様に計３つ作ります。

<figure>
  <img src="{{ '/assets/images/make3d/601/601-26.webp' | relative_url }}" alt="601-26">
</figure>

<figure>
  <img src="{{ '/assets/images/make3d/601/601-27.webp' | relative_url }}" alt="601-27">
</figure>

左右のアルミフレームにホルダーを取り付けます。一度軽く締めて、緩めます。

<figure>
  <img src="{{ '/assets/images/make3d/601/601-28.webp' | relative_url }}" alt="601-28">
</figure>

ケーブルに気を付けながら、下図のようにヒートベッドをホルダーに差し込みます。ヒートベッドの辺の中央にホルダーがくるようにします。

<figure>
  <img src="{{ '/assets/images/make3d/601/601-29.webp' | relative_url }}" alt="601-29">
</figure>

手前のアルミフレームにホルダーを取り付けます。

<figure>
  <img src="{{ '/assets/images/make3d/601/601-30.webp' | relative_url }}" alt="601-30">
</figure>

ヒートベッドの上にベッド（ガラス）を置きます。ガラスホルダーを中央に寄せてボルトを締め、ベッドを固定します。

<figure>
  <img src="{{ '/assets/images/make3d/601/601-31.webp' | relative_url }}" alt="601-31">
</figure>

<figure>
  <img src="{{ '/assets/images/make3d/601/601-32.webp' | relative_url }}" alt="601-32">
</figure>

ATX電源をコンセントに接続し、スイッチをオンにします。LCDが表示されることを確認します。

<figure>
  <img src="{{ '/assets/images/make3d/601/601-33.webp' | relative_url }}" alt="601-33">
</figure>

LCD画面の右上がヒートベッドの表示になります。「現在の温度/設定温度」の形式で表示されます。現在の温度が正しく表示されているか確認します。

※LCD画面左上のホットエンドの温度と若干差があることがあります。２〜３℃の差であれば問題ありません。

注意：表示されている温度が著しく違う場合は、ケーブルが正しくT1に接続されているか、再度確認します。それでも違う場合はお問い合わせください（出荷時に確認はしていますが、輸送中にサーミスタが破損した可能性があります）。
{: .notice--warning}

<figure>
  <img src="{{ '/assets/images/make3d/601/601-34.webp' | relative_url }}" alt="601-34">
</figure>

次に動作確認を行います。LCD右側にあるツマミを押して以下の操作を行います。

Control => Temperature => Bed: => 0を60に変更

<figure>
  <img src="{{ '/assets/images/make3d/601/601-35.webp' | relative_url }}" alt="601-35">
</figure>

<figure>
  <img src="{{ '/assets/images/make3d/601/601-36.webp' | relative_url }}" alt="601-36">
</figure>

<figure>
  <img src="{{ '/assets/images/make3d/601/601-37.webp' | relative_url }}" alt="601-37">
</figure>

<figure>
  <img src="{{ '/assets/images/make3d/601/601-38.webp' | relative_url }}" alt="601-38">
</figure>

<figure>
  <img src="{{ '/assets/images/make3d/601/601-39.webp' | relative_url }}" alt="601-39">
</figure>

最初の画面に戻ると、ヒートベッドの設定温度が６０℃になり、しばらく待つと現在の温度も６０℃になることを確認します。
これで、ヒートベッドが正しく動作することが確認できました。ヒートベッドの温度をゼロに戻します。

<figure>
  <img src="{{ '/assets/images/make3d/601/601-40.webp' | relative_url }}" alt="601-40">
</figure>
