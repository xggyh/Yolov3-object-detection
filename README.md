## YOLOV3：You Only Look Once
---

### 必要な環境
torch == 1.5.0


### トレーニング手順
1.この記事では、トレーニングにVOC形式を使用しています。
2.トレーニングの前に、ラベルファイルをVOCdevkitフォルダーの下のVOC2007フォルダーの下の注釈に配置します。
3.トレーニングの前に、VOCdevkitフォルダーのVOC2007フォルダーのJPEGImagesに画像ファイルを配置します。
4. voc2ssd.pyファイルを使用して、トレーニングの前に対応するテキストを生成します。
5.ルートディレクトリでvoc_annotation.pyを再度実行します実行する前に、クラスを独自のクラスに変更する必要があります。

```python
classes = ["aeroplane", "bicycle", "bird", "boat", "bottle", "bus", "car", "cat", "chair", "cow", "diningtable", "dog", "horse", "motorbike", "person", "pottedplant", "sheep", "sofa", "train", "tvmonitor"]
```
6.対応する2007_train.txtが生成され、各行はその画像の位置と実際のフレームの位置に対応します。
7.トレーニングの前に、model_dataのvoc_classes.txtファイルを変更する必要があります。クラスを独自のクラスに変更する必要があります。
8. utils / config.pyのNUM_CLASSESを、トレーニングが必要なタイプの数と同じになるように変更します。 train.pyを実行してトレーニングを開始します。

### mAPターゲット検出精度計算の更新
get_gt_txt.py、get_dr_txt.py、およびget_map.pyファイルを更新しました。

### Reference
https://github.com/qqwweee/keras-yolo3  
https://github.com/eriklindernoren/PyTorch-YOLOv3   
https://github.com/BobLiu20/YOLOv3_PyTorch
