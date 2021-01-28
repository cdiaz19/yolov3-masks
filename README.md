# 🤖 FaceMask Deep Learning

Final Project to Deep Learning Course (Cenfotec)

## Tech
- TensorFlow 2.0
- Path to install: https://tensorflow2objectdetectioninstallation.readthedocs.io/en/latest/install.html

## Information

We're using 4 mask classes 


| Class       | Description           |
|-------------|-----------------------|
| 0           | With mask             |
| 1           | Without mask          |
| 2           | mask weared incorrect |
| object      |                       |

## Steps

1 - Install last Conda version.
2 - Clone this Repository: https://github.com/zzh8829/yolov3-tf2

## Training

```bash
✨✨✨✨✨✨✨✨
# Tensorflow CPU
conda env create -f conda-cpu.yml
conda activate yolov3-tf2-cpu

# Tensorflow GPU
conda env create -f conda-gpu.yml
conda activate yolov3-tf2-gpu
```

```bash
pip install -r requirements.txt DO NOT RUN THIS. SINCE requirements.txt HAS A DIFFERENT VERSION OF TENSORFLOW
```

```bash
wget https://pjreddie.com/media/files/yolov3.weights -O data/yolov3.weights

python convert.py --weights ./data/yolov3.weights --output ./checkpoints/yolov3.tf

python train.py --dataset ./data/maskschina_train.tfrecord --val_dataset ./data/maskschina_val.tfrecord --classes ./data/masks.names --num_classes 4 --mode fit --transfer darknet --batch_size 8 --epochs 10 --weights ./checkpoints/yolov3.tf --weights_num_classes 80 --yolo_max_boxes 1000

python detect_video.py --video ./data/Mask_video.mp4 --output ./output-loss-13.avi --classes ./data/masks_labeled.names --num_classes 4 --weights ./checkpoints/yolov3_train_9.tf
```

## Dataset on Roboflow

Drive: https://drive.google.com/drive/folders/1aAXDTl5kMPKAHE08WKGP2PifIdc21-ZG?usp=sharing

Database Settings
![Download file on Roboflow](https://github.com/cdiaz19/yolov3-masks/blob/main/media/images/settings.jpg)

Download File
![Download file on Roboflow](https://github.com/cdiaz19/yolov3-masks/blob/main/media/images/downloads.jpg)

## GIF

![GIF](https://github.com/cdiaz19/yolov3-masks/blob/main/media/gifs/gifs.gif)
