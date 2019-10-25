# darknet を使って YOLO によるリアルタイム物体検出を試す

## 事前準備
X を RDP にとばす。
```
export DISPLAY=:10.0
```

## darknet のビルド

```
export PATH=/usr/local/cuda/bin:${PATH}
export LD_LIBRARY_PATH=/usr/local/cuda/lib64:${LD_LIBRARY_PATH}
```

darknet のソースコードを取得する

```
$ git clone https://github.com/pjreddie/darknet.git
$ cd darknet
$ wget https://pjreddie.com/media/files/yolov3-tiny.weights
```

```Makefile``` を編集してGPUを利用するように設定する。

```
GPU=1
CUDNN=1
CUDNN_HALF=1
OPENCV=1
AVX=0
OPENMP=1
LIBSO=1
DEBUG=0
```

```
$ make
```

## 静止画を判定してみる

```
./darknet detect cfg/yolov3-tiny.cfg yolov3-tiny.weights data/dog.jpg
```

## カメラで動画をキャプチャしつつ認識

```
./darknet detector demo cfg/coco.data cfg/yolov3-tiny.cfg yolov3-tiny.weights "'nvarguscamerasrc ! video/x-raw(memory:NVMM), width=1280, height=720, format=(string)NV12, framerate=(fraction)30/1 ! nvtee ! nvvidconv flip-method=2 ! video/x-raw, width=(int)1280, height=(int)720, format=(string)BGRx ! videoconvert ! appsink'"
```