# AI Crack Diagnosis and Length Measurement
```diff
It analyzes the images taken from drone to diagnose cracks of 0.1mm, and builds a model that measures the area and width in pixels.
```


## 0. Table of contents
 [AI Crack Diagnosis and Length Measurement](#ai-crack-diagnosis-and-length-measurement)  
   [Table of contents](#-0-table-of-contents)  
   [Project Description](#-1-project-description)  
   [Technologies](#-2-technologies)  
   [Setup](#-3-setup)  
   [Launch](#-4-launch)  
   [Inspirators](#-5-inspirators)  

## 1. Project Description
### ***Features***
- We use UNet++, DeepLabV3+, HRNetV2 for binary class segmentation.
  - 0: background
  - 1: crack
- Training models for crack segmentation on Crack500, CrackForest, DeepCrack datasets.
- We implemented 3 optimizers [`adam`, `adamw`, `adamp`] and 2 schedulers [`cosine annealing`, `reducelr`].   
  If you want to use other optimizer&scheduler, edit `configure_optimizers` function in `models.py`.   
  Argument `monitor` is essential when you pick reducelr as scheduler.  
- Our model calculate crack width by multiplying the distance between the `skeleton` and the nearest `canny edge` by 2. 
  - Visualization: point on skeleton & point on nearest edge / maximum crack width
- Our model generate and visualize bounding boxes for each contour.   
  Also, it calculate the number of crack pixels in each of the bounding boxes.  
### ***TODOs***
- [ ] Serving PyTorch models with `TorchServe` instead of Flask.
- [ ] Design and Implementation of Advanced Crack Width Detection System


## 2. Technologies
Project is created with:
* Language
  * Python version: 3.9.10
* Library
  * numpy
  * pandas
  * OpenCV
  * PyTorch
  * SegmentationModels
  * matplotlib
  * Albumentations
* Tool
  * Wandb
* Web Framework
  * Flask

## 3. Setup
To run this project, install it locally:
```
$ pip install -U Werkzeug
$ pip install natsort
$ pip install ipywidgets (or 'conda install -c conda-forge ipywidgets')
$ pip install pytorch-lightning
$ pip install segmentation-models-pytorch
```

## 4. Launch
To run a Flask server use this shortcode: `python app.py`  
<img width="80%" src="https://user-images.githubusercontent.com/90584177/198204367-5b7c8eba-7295-433c-802c-59ee2ef86aa7.gif"/>

## 5. Inspirators
This project is based on 'PyTorch-Lightning template for semantic segmentation' from https://github.com/GunwooHan/PyTorch-Lightning_Template_for_Semantic_Segmentation
