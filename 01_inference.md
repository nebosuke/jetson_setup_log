# jetson-inference を試す

## インストールとビルド
```
$ cd Documents
$ git clone https://github.com/dusty-nv/jetson-inference
$ cd jetson-inference/
$ git submodule update --init
$ mkdir build
$ cd build
$ cmake ..
```

インストール時にダウンロードする学習済みモデルの選択画面が開くので、特に選択を変更せずに試しにダウンロードする。

![Model Downloader](images/jetson-inference-downloader.png)

ダウンロード中

![Downloading](images/jetson-inference-downloading.png)

PyTorch の選択
![PyTorch](images/jetson-inference-pytorch.png)

いまはもう Python 3.6 で選択しておく。

```
$ make
```

ビルド中
![make](images/jetson-inference-make.png)

```
$ sudo make install
```

## デモプログラムを試してみる

RDPで繋いだデスクトップ環境で実行する。

```
$ cd ~/Documents/jetson-inference/build/aarch64/bin
$ eog images/orange_0.jpg
```

```
$ imagenet_console images/orange_0.jpg images/output_0.jpg
```

![imagenet-console](images/jetson-inference-imagenet.png)

結果を確認
```
$ eog images/output_0.jpg
```

![imagenet-console](images/jetson-inference-output.png)

97.891% でオレンジ
