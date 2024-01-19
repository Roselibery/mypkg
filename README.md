# mypkg

* 本リポジトリは，二つのノード間で通信をするROS2のパッケージです．
* パブリッシャ（talkerノード）から``/countup``トピックにプッシュされた数字データをサブスクライバ（listenerノード）がサブスクライブし，表示するものです．
* 本リポジトリを使用するにはROS2をあらかじめインストールしている必要があります．
* 本リポジトリは，2023年度の千葉工業大学先進工学部未来ロボティクス学科のロボットシステム学の講義で取り扱われた練習用のリポジトリです．

## ノード一覧
* Talker(``talker``) : パブリッシャを持つノードです．0.5秒ごとに数字を0から一つずつ加算して，``/countup``トピックにプッシュします．
* listener(``listener``) : サブスクライバを持つノードです．``/countup``トピックから数字を受信して表示します．
## トピック
* ``countup`` : 16ビットの符号付き整数のトピックです．
  
## 機能
* Talk_Listen(talk_listen.launch.py) : パブリッシャ（talker）とサブスクライバ(listener)を一つの端末で両方起動させるlaunchファイルです．
## 実行方法
実行方法は二つあります．ROS2が導入されている環境で実行してください．いずれも終了する際は``Ctr + C``で終了してください．
* 一つの端末でトピックのパブリッシャとサブスクライバの両方を実行する
  以下のコマンドを実行するとパブリッシャ（talker）とサブスクライバ(listener)を起動します．
  ```
  $ ros2 launch mypkg talk_listen.launch.py
  ```
* 複数の端末を用いてパブリッシャとサブスクライバを個別に実行する
 以下のコマンドを別々の端末でそれぞれ実行してください．
  * パブリッシャ（talker）を実行するコマンド
  ```
  $ ros2 run mypkg talker
  ```
  * サブスクライバ（listener）を実行するコマンド
  ```
  $ ros2 run mypkg listener
  ```
## 実行例
```
[INFO] [launch]: All log files can be found below /home/rosel/.ros/log/2024-01-19-14-58-40-044320-YURI_03-1062
[INFO] [launch]: Default logging verbosity is set to INFO
[INFO] [talker-1]: process started with pid [1064]
[INFO] [listener-2]: process started with pid [1066]
[listener-2] [INFO] [1705643921.364426930] [listener]: Listen: 0
[listener-2] [INFO] [1705643921.796095047] [listener]: Listen: 1
[listener-2] [INFO] [1705643922.295790025] [listener]: Listen: 2
[listener-2] [INFO] [1705643922.795988882] [listener]: Listen: 3
[listener-2] [INFO] [1705643923.295943490] [listener]: Listen: 4
[listener-2] [INFO] [1705643923.795786762] [listener]: Listen: 5
[listener-2] [INFO] [1705643924.295935749] [listener]: Listen: 6
[listener-2] [INFO] [1705643924.795871823] [listener]: Listen: 7
[listener-2] [INFO] [1705643925.295977689] [listener]: Listen: 8
[listener-2] [INFO] [1705643925.796168330] [listener]: Listen: 9
[listener-2] [INFO] [1705643926.294769630] [listener]: Listen: 10
```
## 必要なソフトウェア
* Python3
  * テスト済み
* ROS2
  * version:foxy

## テスト環境
* Ubuntu 20.04

## ライセンス
* このソフトウェアパッケージは，3条項BSDライセンスの下，再頒布および使用が許可されます．
* このパッケージのコードは，下記のスライド（CC-BY-SA 4.0 by Ryuichi Ueda）のものを，本人の許可を得て自身の著作としたものです．
     * [ryuichiueda/my_slides/robosys_2022](https://github.com/ryuichiueda/my_slides/tree/master/robosys_2022)
* © 2024 Yuri Sawada
