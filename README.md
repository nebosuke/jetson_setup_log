# Jetson Nano ハンズオン

## Jetson Nano とは
NVIDIAが開発している、GPUがのっかったエッジコンピューティングマシン。
NVIDIAなのでCUDAが利用可能なので、外出先でもGPUプログラミングができる夢のマシン。

- [00_setup.md](00_setup.md) 電源を入れてSSHで接続できるようになるところまで
- [01_inference.md](01_inference.md) jetson-inference を試す
- [02_visionworks.md](02_visionworks.md) VisionWorks で動画から物体追跡を試す
- [03_vscode.md](03_vscode.md) PCのVS CodeでJetson上のファイルを編集できるようにする
- [04_inference_2.md](04_inference_2.md) 自分でモデルを利用するコードを作成してみる

## ハンズオン
- [10_adduser.md](10_adduser.md) ハンズオン用に自分のアカウントを Jetson Nano に作成する
- [11_camera.md](11_camera.md) カメラをつかって画像をキャプチャする
- [12_darknet.md](12_darknet.md) darknetで物体検知
- [13_inference.md](13_inference.md) jetson-inferenceで物体検知
- カメラでキャプチャした画像から画像認識モデルをつかって何が写っているのかを判定する
- カメラでキャプチャした画像に何人の人が含まれているのかを判定する

JetCardからやり直しだけれども、これも試してみたい。
https://www.space-i.com/post-blog/jetson-nanoでdeepstream-sdk%E3%80%80usbカメラ映像から検知＆iphoneでストリーム/

- [20_install_tensorflow.md](20_install_tensorflow.md) TensorFlowをインストール
