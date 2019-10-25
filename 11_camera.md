# カメラの画像をキャプチャする

Jetson Nano の基盤上にある J13 の端子には、Raspberry Pi 用のカメラ (v2) が接続できる。

## 注意事項
- **コネクタの操作は極めて壊れやすいので最新の注意が必要**
- **作業の前にシャットダウンしてACアダプタを抜いておく**

## 作業手順

### Jetson Nano のシャットダウン
```
$ sudo shutdown -h now
```

ACアダプタを外す。

### カメラを接続

コネクタはちょっと強く引っ張るとすぐに壊れる。**慎重に**。

![Etcher](images/11_camera_connector.jpeg)

カメラを接続して Jetson Nano を起動すると、特にドライバ等のセットアップも必要なく ```/dev/video0``` というデバイスが出現する。

### カメラで動画を撮影してRTSPで配信してみる

デバイスとして認識されていれば ```/dev/video0``` として見えているはず。

```
$ ls -l /dev/video0
crw-rw----+ 1 root video 81, 0 Oct 24 16:38 /dev/video0
```
