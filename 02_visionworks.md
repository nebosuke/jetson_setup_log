# VisionWorksをビルドして物体追跡を試す

Jetcard の中にソースが含まれているのでそこからビルドする。

```
$ cd ~/Documents
$ mkdir visionworks
$ cd /usr/share/visionworks/sources
$ ./install-samples.sh ~/Documents/visionworks
$ cd ~/Documents/visionworks/VisionWorks-1.6-Samples
$ make
```

入力動画をみてみる

```
$ totem ./data/cars.mp4
```

RDP 経由だと遅いので全画面表示になっているときは、それを解除する。

