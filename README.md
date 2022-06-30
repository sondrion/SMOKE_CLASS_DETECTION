# SMOKE_CLASS_DETECTION
## <div align="center">Table of content</div>
- [Install LIBRAIRIES](#Install-LIBRAIRIES)
- [Load Model Yolov5](#Load-Model-Yolov5)
- [Dataset](#dataset)
- [Training](#Training)
- [Performances](#Performances)
- [Results](#Results)
## <div align="center">Install LIBRAIRIES</div>
Clone repo and install [requirements.txt](https://github.com/ultralytics/yolov5/blob/master/requirements.txt) in a
[**Python>=3.7.0**](https://www.python.org/) environment, including
[**PyTorch>=1.7**](https://pytorch.org/get-started/locally/)
```bash
git clone https://github.com/ultralytics/yolov5  # clone
cd yolov5
pip install -r requirements.txt  # install
```
## <div align="center">load model Yolov5</div>
[Models](https://github.com/ultralytics/yolov5/tree/master/models) download automatically from the latest
YOLOv5 [release](https://github.com/ultralytics/yolov5/releases)
```python
import torch

# Model
model = torch.hub.load('ultralytics/yolov5', 'yolov5s')  # or yolov5n - yolov5x6, custom

# Images
img = 'https://img.freepik.com/photos-gratuite/fumee-industrielle-dans-atmosphere_33799-3042.jpg?w=1380'  # or file, Path, PIL, OpenCV, numpy, list

# Inference
results = model(img)

# Results
results.print()  # or .show(), .save(), .crop(), .pandas(), etc.
```
## <div align="center">Dataset</div>
we imported 12336 unlabeled images from kaggle, we labeled 100 images using two classes: 'smoke low density' and 'smoke high density'
The same database we found already labeled, with a single class 'smoke'.
<div align="center"><img width="800" src="https://github.com/sondrion/SMOKE_CLASS_DETECTION/blob/186b0cfe7133dd80eddd7a8cb64eaa3753707aa1/photo.PNG">
## <div align="center">Training</div>
We installed [wandb](https://wandb.ai/site) to visualize the results directly on the website by creating an account
```bash
%pip install -q wandb
import wandb
wandb.login()
```
The commands below reproduce YOLOv5 [data](https://github.com/sondrion/SMOKE_CLASS_DETECTION/blob/89a3d7a90d613f312a9f253d2d0e2216b3b35e53/data.rar)
results. [Models](https://github.com/ultralytics/yolov5/tree/master/models) download automatically from the latest
YOLOv5 [release](https://github.com/ultralytics/yolov5/releases)
```bash
python train.py --data data.yaml --cfg yolov5s.yaml --weights '' --batch-size 64

```
















