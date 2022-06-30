# SMOKE_CLASS_DETECTION
## <div align="center">Table of content</div>
- [Install LIBRAIRIES](#Install-LIBRAIRIES)
- [Load Model Yolov5](#Load-Model-Yolov5)
- [Dataset](#dataset)
- [Training](#Training)
- [Performances](#Performances)
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
<img width="800" src="https://user-images.githubusercontent.com/photo.PNG">
## <div align="center">Training</div>
We installed [wandb](https://wandb.ai/site) to visualize the results directly on the website by creating an account
```bash
%pip install -q wandb
import wandb
wandb.login()
```
The commands below reproduce YOLOv5 [data](https://github.com/sondrion/yolov5/blob/master/data/scripts/get_coco.sh)
results. [Models](https://github.com/ultralytics/yolov5/tree/master/models) download automatically from the latest
YOLOv5 [release](https://github.com/ultralytics/yolov5/releases)
```bash
python train.py --data data.yaml --cfg yolov5s.yaml --weights '' --batch-size 64

```
## <div align="center">Performances</div>
<img width="800" src="https://user-images.githubusercontent.com/26833433/90222759-949d8800-ddc1-11ea-9fa1-1c97eed2b963.png">
<img width="800" src="https://user-images.githubusercontent.com/26833433/90222759-949d8800-ddc1-11ea-9fa1-1c97eed2b963.png">
<img width="800" src="https://user-images.githubusercontent.com/26833433/90222759-949d8800-ddc1-11ea-9fa1-1c97eed2b963.png">
<img width="800" src="https://user-images.githubusercontent.com/26833433/90222759-949d8800-ddc1-11ea-9fa1-1c97eed2b963.png">












