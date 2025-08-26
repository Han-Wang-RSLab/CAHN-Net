# CAHN-Net: Content-Adaptive Hierarchical Network for Cross-Modal Remote Sensing Object Detection

By Han Wang, Yiqing Li, and Wen Zhou

This repository contains the implementation accompanying our paper FDKD-Net: Diffusion-Based Feature Fusion with Dual-Path Knowledge Transfer for Aerial Remote Sensing Detection.

If you find this project helpful, please consider giving it a star ⭐


![](https://github.com/Han-Wang-RSLab/CAHN-Net/blob/main/CAHN-Net-main/figs/01.png)

 We leave our system information for reference.

    python: 3.10.14
    torch: 2.2.2+cu121
    torchvision: 0.17.2+cu121
    timm: 0.9.8
    mmcv: 2.2.0
    mmengine: 0.10.4
    trition: 3.2.0

Other operating environments    

pip install timm==1.0.7 thop efficientnet_pytorch==0.7.1 einops grad-cam==1.5.4 dill==0.3.8 albumentations==1.4.11 pytorch_wavelets==1.3.0 tidecv PyWavelets opencv-python prettytable -i https://pypi.tuna.tsinghua.edu.cn/simple

## Dataset Preparation
Please construct the datasets following these steps:

- Download the datasets from their sources. 
You can download the processed xView and VisDrone-Datasets and HIT-UAV-Datasets  from this Web [link](https://github.com/VisDrone/VisDrone-Dataset) and [link](https://github.com/suojiashun/HIT-UAV-Infrared-Thermal-Dataset).

- Convert the annotation files into TXT-format annotations.

- Modify the dataset path setting within the script.

```
'dateset's name': {
    'train_img'  : '',  #train image dir
    'train_Label' : '',  #train txt format label file
    'val_img'    : '',  #val image dir
    'val_label'   : '',  #val txt format label file
},
```
- Add domain adaptation direction within the script [__init__.py](./datasets/__init__.py). During training, the domain adaptation direction will be automatically parsed and corresponding data will be loaded. In our paper, we provide four adaptation directions for remote sensing scenarios.
```

```

## Training / Evaluation / Inference
We provide training script on single node as follows.
- Training with single GPU
```
python train.py
```
- Valing with dataset
python val.py
```
- Self-distillation process
```
python distill.py
```
- get_COCO_metrice
```
get_COCO_metrice.py
## Experiments Result  

![](https://github.com/Han-Wang-RSLab/CAHN-Net/blob/main/CAHN-Net-main/figs/02.png)
## Demo prediction

![](https://github.com/Han-Wang-RSLab/CAHN-Net/blob/main/CAHN-Net-main/figs/03.png)

