# 🪄 CV Track : Deep Learning Project
- Segmentation X-Ray medical images using custom U-Net model(DoubleUNet)
  
  
    
### Context
---
***1. train image / label image***

<img src = "https://user-images.githubusercontent.com/90584177/182973699-7b273eda-103f-49a4-8889-dafc4d89979b.jpg" alt="train image" style="width:300px;"/> <img src = "https://user-images.githubusercontent.com/90584177/182973752-e04a931e-560b-4562-9525-8de4b89e3b23.png" alt="train image" style="width:300px;"/>


***2. class***
    - 1 : air         (RED)
    - 0 : background  (BLACK)
      
  
      
### Content
---
***1. dataset structure***

data split|# of original images|# of images using elastic deformations
|:-----:|:----:|:----:
train(image + label)|78|-
validation(image+label)|10|-
test(image+label)|9|-



***2. Overview of files***
- [x] DoubleUNet.py : Define custom U-Net model  
- [x] unet(elastic_deformation).ipynb : live lecture material  
- [x] semantic_segmentation_multi_class.ipynb : online course material  
- [ ] DoubleUNet.ipynb : work result  
  
  
### Require an amendments
---
1. I can't figure out input/output ***tensor size*** when using a class or user-difined function with input and output.  
2. So, It's hard to generate DoubleUNet model  
     - fine tune U-Net  
     - get the gradient of loss function twice  
3. I wanted to implement dice loss and BCE Loss function simultaneously in 'UNet_metric' class,      
   but only succeed in implementing dice loss function  
4. For the reasons above, training code doesn't work.  
