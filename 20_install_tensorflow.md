# TensorFlowのインストール

NVIDIAが標準パッケージで TensorFlow の pip パッケージを公開しているので、以下のページの手順どおりにインストールできる。

https://docs.nvidia.com/deeplearning/frameworks/install-tf-jetson-platform/index.html

```
$ sudo apt-get install libhdf5-serial-dev hdf5-tools libhdf5-dev zlib1g-dev zip libjpeg8-dev
```

Python3 の pip をインストール。

```
$ sudo apt-get install python3-pip
```

必要な Python のパッケージをインストール。

```
$ sudo pip3 install -U numpy==1.16.1 future==0.17.1 mock==3.0.5 h5py==2.9.0 keras_preprocessing==1.0.5 keras_applications==1.0.8 gast==0.2.2 enum34 futures testresources setuptools protobuf
```

TensorFlow をインストール。

```
$ sudo pip3 install --pre --extra-index-url https://developer.download.nvidia.com/compute/redist/jp/v42 tensorflow-gpu
```

動作を確認

```
$ python3
Python 3.6.8 (default, Oct  7 2019, 12:59:55)
[GCC 8.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import tensorflow as tf
>>> tf.__version__
'1.13.1'
```

1.13.1 がインストールされた。
