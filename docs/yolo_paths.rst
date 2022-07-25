.. _yolopaths:

Разметка. Блоки, использующие фаловые пути
===================================================

Файл YOLOv5.ipynb:
--------------------------
**#2**
::

    !cp **./drive/MyDrive/VisionProject/NewDataset/CleanedNewLabels.json** ./coco_annotations.json

**#6**
::

    ARUCO_DATASET_DIR = '**/content/drive/MyDrive/VisionProject/NewDataset/Data/**

**#19**
::

    !cp **./drive/MyDrive/VisionProject/Model/coco128.yaml** ./yolov5/data/coco128.yaml

**#25**
::

    !mv /content/yolov5/runs/train/exp/weights/last.pt **/content/drive/MyDrive/VisionProject/Model/Marking.pt**

**#26**
::

    !cp **/content/drive/MyDrive/VisionProject/Model/Marking.pt** /content/yolov5/weight1.pt

**#29**
::

    !python detect.py --source **/content/drive/MyDrive/VisionProject/Videos/video2.mp4** --weights /content/yolov5/weight1.pt --img 416 --save-txt --save-conf

**#31**
::

    !mv /content/yolov5/runs/detect/exp/video2.mp4 **/content/drive/MyDrive/VisionProject/Resault/video2.mp4**


Файл YOLOv3.ipynb:
--------------------------

**#2**
::

    !cp **./drive/MyDrive/VisionProject/NewDataset/CleanedNewLabels.json** ./coco_annotations.json

**#6**
::

    ARUCO_DATASET_DIR = '**/content/drive/MyDrive/VisionProject/NewDataset/Data/**'

**#21**
::

    !cp **./drive/MyDrive/VisionProject/Model/coco128.yaml** ./yolov3/data/coco128.yaml

**#28**
::

    !mv /content/yolov3/runs/train/exp/weights/last.pt **/content/drive/MyDrive/VisionProject/Model/Marking_v3.pt**

**#29**
::

    !cp **/content/drive/MyDrive/VisionProject/Model/Marking_v3.pt** /content/yolov3/weight1.pt

**#31**
::

    !python detect.py --source **/content/drive/MyDrive/VisionProject/Videos/video2.mp4** --weights /content/yolov3/weight1.pt --img 416 --save-txt --save-conf

**#32**
::

    !mv /content/yolov3/runs/detect/exp/video2.mp4 **/content/drive/MyDrive/VisionProject/Resault/video2_v3.mp4**


Файл YOLOv3tiny.ipynb:
--------------------------

**#2**
::

    !cp **./drive/MyDrive/VisionProject/NewDataset/CleanedNewLabels.json** ./coco_annotations.json

**#6**
::

    ARUCO_DATASET_DIR = '**/content/drive/MyDrive/VisionProject/NewDataset/Data/**'

**#19**
::

    !cp **./drive/MyDrive/VisionProject/Model/coco128.yaml** ./yolov3/data/coco128.yaml

**#27**
::

    !mv /content/yolov3/runs/train/exp/weights/last.pt **/content/drive/MyDrive/VisionProject/Model/Marking_v3tiny.pt**

**#28**
::

    !cp **/content/drive/MyDrive/VisionProject/Model/Marking_v3tiny.pt** /content/yolov3/weight1.pt

**#30**
::

    !python detect.py --source **/content/drive/MyDrive/VisionProject/Videos/video2.mp4** --weights /content/yolov3/weight1.pt --img 416 --save-txt --save-conf

**#31**
::

    !mv /content/yolov3/runs/detect/exp/video2.mp4 **/content/drive/MyDrive/VisionProject/Resault/video2_v3tiny.mp4**