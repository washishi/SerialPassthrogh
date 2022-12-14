ｽﾀｯｸﾁｬﾝ SCサーボモデル用 シリアルパススループログラム

概要
・ｽﾀｯｸﾁｬﾝ SCサーボモデルに使われるサーボ(FEETECH SCS0009)の
  設定には通常インターフェースボードFE-URT-1を利用しますが
　ｽﾀｯｸﾁｬﾝの基板にはSCサーボと通信できる信号変換機能がある為
  ｽﾀｯｸﾁｬﾝ(M5Stack)のUSBシリアルからそちらへパススルーするこ
　とによりFE-URT-1がなくてもサーボの設定等が行える様にした
  ものです

・必要なもの
  ・ｽﾀｯｸﾁｬﾝ SCサーボ(FEITECH SCS0009)のモデル(もしくは基板)
     https://github.com/meganetaaan/stack-chan
  ・Arduino IDE で ｽﾀｯｸﾁｬﾝ(M5Stack) に書き込める環境
     https://www.arduino.cc/en/software
  ・FT-SCServoDebugツール(英語版)
    (秋月のFE-URT-1のページからDLしました、1次配布先は不明)

・利用方法
　・Arduino IDE で SerialPassthrough.ino を開き
    ｽﾀｯｸﾁｬﾝ SCサーボモデル(M5Stack) に書き込む
　・FT-SCServoDebugツールを立ち上げて
　　・Com Settings で ｽﾀｯｸﾁｬﾝ(M5Stack)の繋がっている
      Comポートを選択
  　・BaudRは115200にして「Open」ボタンを押す
  　・ServoListの「Search」ボタンを押すとｽﾀｯｸﾁｬﾝに内蔵された
      SCサーボが2つ見つかるので「Stop」ボタンを押してサーチを
      停止します
  　あとはFE-URT-1を利用する場合と操作は同じです
  　※サーボが検出されない場合は一度ｽﾀｯｸﾁｬﾝ(M5Stack)の電源
      スイッチを押してリセットしてみてください
  　※購入したまま(ID:1)のサーボが2つ接続されている場合は検出
      できませんのでID:1のままで良いパン(左右＝足)のサーボの
      コネクタを一時的に取り外してチルト(上下)のサーボのIDを
      2に変更してください

利点
・インターフェースボードFE-URT-1が不要
・サーボのコネクタを外さなくてもサーボの稼働範囲等の設定を
  変更することができる

難点、制限事項等
・使用した後はｽﾀｯｸﾁｬﾝ(M5Stack)のfirmwareを入れなおす必要が
  ある
・USBシリアルが115200bpsでSCサーボとの通信が1000000bpsと
  大きな速度差があるためタイムアウトが発生します
　その為スライダーによる連続変更等はスムーズに動きません
  (USBシリアルの速度をもっと上げれば改善すると思われるが
   PCのドライバ設定の変更等が必要になるため未実施)

