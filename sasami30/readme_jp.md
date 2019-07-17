# 3x10 ortholinear keyboard

![sasami30](image/sasami30.jpg)

## 必要なパーツ
| 名前 | 数 | 備考 | 調達先の例 | 参考価格（送料込） |
|:-|:-|:-|--|--|
| SU120 PCB | 2枚 | [入手方法はこちら](../common/pcb_order_guide_jp.md) | [Elecrow Online store](https://www.elecrow.com/) | 10枚で1,400円($12.94) |
| Pro Micro | 1個 | スルーホールをZigzag仕様にしてあるのでコンスルーではなく普通の付属ピンヘッダを使います | [AliExpress](https://www.aliexpress.com/)で「Pro Micro ATmega32U4 5V 16MHz」を検索 | 290円($2.66) |
| タクトスイッチ 2本足のもの | 1個 | | https://www.amazon.co.jp/dp/B00QLTSZK6 | 50個で184円 |
| ダイオード 1N4148 | 30個 | ハンダ付けの難易度は上がりますが表面実装ダイオード(1N4148W)も可 | https://www.amazon.co.jp/dp/B06WWJ76D7 | 500個で313円 |
| LEDテープ お好みの長さ | 1本 | WS2812Bを使用したもの | https://www.aliexpress.com/item/32682015405.html | 1mで500円($4.57) |
| Kailh PCBソケット CherryMX用 または Choc用 | 30個 | | https://yushakobo.jp/shop/a01ps/ | 450円+送料300円 |
| 5ピン仕様のキースイッチ CherryMX用 または Choc用 | 30個 |  | https://yushakobo.jp/product-category/switches/ | 1200円～ |
| キーキャップ CherryMX用 または Choc用 | 30個 |  | CherryMX用 https://ja.aliexpress.com/item/32851511530.html | 40個で670円($6.20～) |
| クッションゴム | 6個 |  | ダイソー クッションゴム 14個入り または すべりどめシート | 108円 |
| M1.4ネジ 3.5mm長 | 2本 |  | https://www.aliexpress.com/item/32995302870.html | 100本で110円($0.99) |
| Micro USBケーブル | 1本 | 通信ができるもの | ダイソー | 108円 |
| 計 |  |  |  | 5,633円 |

## 使用する道具、消耗品

[使用する道具、消耗品](../common/tool_guide_jp.md)を参照ください。

## ビルドガイド

### Pro Microのもげ防止加工

Pro Microにエポキシ接着剤を盛って、簡単にはもげないようにします。

参考1:[ProMicroのモゲ防止ついでにQMK_Firmwareを書き込む - Qiita](https://qiita.com/hdbx/items/2f3e4ddfcadda2a5578e)
参考2:[もげ予防 - Self-Made Keyboards in Japan](https://scrapbox.io/self-made-kbds-ja/%E3%82%82%E3%81%92%E4%BA%88%E9%98%B2)

エポキシ接着剤の2液を混ぜます。

![adhesive_prepare](../common/image/promicro_adhesive_prepare.jpg)

接着剤を付け始める前にMicro USBコネクタを横から見てください。側面に穴が開いています。この穴に接着剤が入ると端子が入らなくなったり、入りにくくなったりします。

![usb_side_hole](../common/image/promicro_usb_side_hole.jpg)

この穴を避けて、つまようじなどで接着剤を盛っていきます。

![promicro_pate](../common/image/promicro_pate.jpg)

乾くまで置いておきます。

### 基板のカット

![pcb_cut](image/pcb_cut.jpg)

最終的に上の図のようにカットします。

まず基板端のビスケットをニッパーで切断します。切ってよい場所は印を付けているので、印の付いているところだけ切断してください。

![biscuits_cut](../common/image/biscuits_cut.jpg)

次に、不要な行を切断します。

![cut_row](image/cut_row.jpg)

行ごと切断するには、ニッパーで表裏に切れ目を入れてから机の端などで折り割ってください。

![cut_line_1](../common/image/cut_line_1.jpg)

![cut_line_2](../common/image/cut_line_2.jpg)

最後に、L字型に切断します。ハンドソーで青いラインを切ったあと、赤いラインにニッパーで切れ目を入れて折り割ってください。

![cut_l_shape](image/cut_l_shape.jpg)

### 基板側面のヤスリがけ

机に紙ヤスリを置き、その上で基板の側面をヤスリがけします。粗目だけでもそこそこきれいになります。お好みで細目までかけてもよいです。

![sand_pcb](../common/image/sand_pcb.jpg)

![sand_pcb2](../common/image/sand_pcb2.jpg)

![sand_pcb3](../common/image/sand_pcb3.jpg)

### 基板の結合

M1.4ネジとビスケットで基板を結合させます。ネジ頭とビスケットが干渉しないように、基板の裏からネジ止めします。

![connect_pcb](../common/image/connect_pcb.jpg)

基板の表面のネジ先をハンダ付けすると多少強度が上がります。

![solder_screw_hole](../common/image/solder_screw_hole.jpg)

続けて基板間の回路を接続します。接続する場所は以下の3箇所です。

![connect_circuit](image/connect_circuit.jpg)

ダイオードの足を切って、コの字に折り曲げます。

![bend_wire](../common/image/bend_wire.jpg)

基板間のROWと書かれたスルーホールをコの字に曲げた針金で繋ぎます。

![connect_row](../common/image/connect_row.jpg)

ハンダ付けして飛び出た部分を切ります。または飛び出た部分を切ってからハンダ付けします。

![solder_row_wire](../common/image/solder_row_wire.jpg)

### ダイオードの取り付け

各キースイッチの端の30箇所にダイオードを取り付けます。

キースイッチの枠が描いてあるほうが基板の表で、Kailh PCBソケットの枠が描いてあるほうが裏です。

ダイオードは、基板の表と裏、どちら側に付けても構いません。ただし、ロープロファイルスイッチで将来的にトッププレートを付けたい場合は、以下のいずれかを選択してください。

- 基板の裏側にダイオードを付け、表側に出た足をカットしてからハンダ付けする
- 基板の裏側に表面実装ダイオードをハンダ付けする

ダイオードの足は、指で根本付近を曲げます。はじめに1つだけダイオードを曲げて穴に差し込んでみて、うまくいく曲げ具合を確認して残りのダイオードを同じように曲げてください。

![diode_bent](../common/image/diode_bent.jpg)

ダイオードの黒くなっている側が、基板の図の二重線の側になるように差し込みます。

![diode_inserted](../common/image/diode_inserted.jpg)

全てのダイオードを配置した後、マスキングテープで浮かないようにカバーしておきます。

![diode_taped](../common/image/diode_taped.jpg)

基板をひっくり返してダイオードを全てハンダ付けし、ニッパーで足を切ります。ダイオードの足を切ってからハンダ付けしても構いません。私はハンダ付けのときに周りの足が邪魔なのと、後がきれいになるので、最近はカットしてからハンダ付けするようにしています。

![diode_soldered](../common/image/diode_soldered.jpg)

### PCBソケットの取り付け

基板の裏の印刷された枠に合うようにPCBソケットを配置します。
CherryMX用のPCBソケットを置く場合は、間違った向きに置かないように注意してください。間違った向きに取り付けるとあとでキースイッチが入りません。

![socket_attached](../common/image/socket_attached.jpg)
![socket_attached_all](../common/image/socket_attached_all.jpg)

PCBソケット両端の金属部分をハンダ付けします。

![socket_soldered](../common/image/socket_soldered.jpg)

### GNDのジャンパ

基板の裏側のジャンパ3箇所をハンダ付けします。**表側にもジャンパがありますが、裏側のみハンダ付けします**。

![jumper](../common/image/jumper.jpg)

ハンダを盛ってから間を繋ぐのですが、うまくいかない場合はダイオードの切れ端を使って繋いでも構いません。

![jumper_wire](../common/image/jumper_wire.jpg)

![jumper_wire2](../common/image/jumper_wire2.jpg)

### リセットスイッチの取り付け

基板の表側からタクトスイッチをはめ込みます。

![reset_switch](../common/image/reset_switch.jpg)

裏返してハンダ付けします。

### Pro Microの取り付け

基板の表側のPro Micro設置部分の2箇所に、Pro Microに付属している12ピンのピンヘッダの短い側を根本まで差し込みます。

![pin_header_attach](../common/image/pin_header_attach.jpg)

スルーホールがジグザグになっているので、少し入れにくくなっています。ゆっくり押し込んでください。

ピンヘッダにPro Microを差し込みます。**Pro Microの裏面（平らなほう）が上になるように、またマイクロUSBが基板端になるように**します。

**向きを間違えるとリカバリーが大変です。表裏、左右をよく確認してください。**

ニッパーでピンヘッダの足を切ってからPro Microとピンヘッダをハンダ付けします。まず四隅をハンダ付けし、横から見てピンヘッダとの間に隙間があれば押さえながらハンダを温めて浮かないようにします。そのあと、順番に全てハンダ付けします。

![pinheader_cut](../common/image/pinheader_cut.jpg)

基板とピンヘッダはジグザグのスルーホールで接触しているため、ハンダ付けは不要です。

### キースイッチの取り付け

表側から差し込みます。キースイッチの足が曲がっている場合はまっすぐにしてから差し込んでください。

![switch_attach](../common/image/switch_attach.jpg)


### キーキャップの取り付け

キースイッチにキーキャップをはめます。

![keycap_attach](image/keycap_attach.jpg)

### ゴム足の取り付け

ゴム足を裏面に取り付けます。ソケットやキースイッチに接触する場合はハサミで切ってから取り付けます。

![rubber_foot](../common/image/rubber_foot.jpg)

試打してみて、基板のたわみが気になればゴム足を増やしてください。

### ファームウェアの書き込み

まず、以下のリンク先を参考にして、QMK Firmwareのビルド環境を用意します。
- [プログラマーではない人向けのQMK Firmware入門 - Qiita](https://qiita.com/cactusman/items/ac41993d1682c6d8a12e)
- [Getting Started - QMK Firmware](https://docs.qmk.fm/#/newbs_getting_started)

ビルド環境構築時に持ってくるQMK Firmwareは、フォークした[https://github.com/e3w2q/qmk_firmware/tree/su120](https://github.com/e3w2q/qmk_firmware/tree/su120)とします。または、本家を持ってきて、そこに[https://github.com/e3w2q/qmk_firmware/tree/su120/keyboards/handwired/su120](https://github.com/e3w2q/qmk_firmware/tree/su120/keyboards/handwired/su120)以下をコピーしてもよいです。

用意されたキーマップを書き込むにはqmk_firmwareのフォルダに移動し、以下を実行します。

```
make handwired/su120/rev1:sasami30:avrdude  
```

**Detecting USB port, reset your controller now...** と表示されたらPro Micro横にハンダ付けしたリセットスイッチを押すと書き込みが始まります。

[KeyboardTester.com](https://www.keyboardtester.com/tester.html)等でキー入力が行えるかテストしてください。