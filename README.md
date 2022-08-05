# CV Track : Deep Learning Project 
- Segmentation X-Ray medical images using custom U-Net model(DoubleUNet)


### Context
---
![train image](https://user-images.githubusercontent.com/90584177/182973699-7b273eda-103f-49a4-8889-dafc4d89979b.jpg)
![label](https://user-images.githubusercontent.com/90584177/182973752-e04a931e-560b-4562-9525-8de4b89e3b23.png)  
- class
    - 1 : air
    - 2 : background
    
    
### Content
---
data split|# of original images|# of images using elastic deformations
|:-----:|:----:|:----:
train(image + label)|78|-
validation(image+label)|10|-
test(image+label)|9|-



### Require an amendments
---
1. I can't figure out input/output <span style = 'background-color: #fff561'>tensor size</span> when using a class or user-difined function with input and output.
2. So, It's hard to generate DoubleUNet model
     - fine tune U-Net
     - get the gradient of loss function twice
3. I wanted to implement dice loss and BCE Loss function simultaneously in 'UNet_metric' class,   
   but only succeed in implementing dice loss function
4. For the reasons above, training code doesn't work.
