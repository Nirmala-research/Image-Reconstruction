# Image-Reconstruction Technique
  Medical Image Reconstruction - Dermoscopic images

## Overview
  An official implementation of a Single image reconstruction technique for Melanoma Skin lesion images for feature extraction using PyTorch.

## Requirments
  Matlab R2019
  
  Python 3.10.10
  
  PyTorch 1.4
  
  Pillow 5.1.0
  
  scikit-image 0.19.3
  
  numpy 1.14.5
  
  This was tested on Python 3.7. To install the required packages, use the provided requirements.txt file like so:
            
```
pip install -r requirements.txt
```
            

## Datasets
  ISIC Challenge Datasets 2020  https://challenge.isic-archive.com/data/#2020
  
  PH2 Dataset https://www.dropbox.com/s/k88qukc20ljnbuo/PH2Dataset.rar
## Pre-trained model
  MELLiResNet 
  
  MELIIGAN
  
  https://drive.google.com/file/d/1FV0T8C_0Z6oMUuvOq9ELs6EsXqxLuS5O/view?usp=share_link
## Input Size changing
The provided model was trained on ISIC 2019, PH2 dataset and mednode image inputs, but to run it on inputs of arbitrary size, you'll have to change the input shape as given.
```
from tensorflow import keras

# Load the model
model = keras.models.load_model('models/generator.h5')

# Define arbitrary spatial dims, and 3 channels.
inputs = keras.Input((None, None, 3))

# Trace out the graph using the input:
outputs = model(inputs)

# Override the model:
model = keras.models.Model(inputs, outputs)

# Now you are free to predict on images of any size.
```
## Experimental Results
  The experimental results on the benchmark datasets.
  ### Quantitave Results
  | Algorithm|  | Bicubic | ESPCN | SRGAN | ESRGAN | MELIIGAN (MY model)|
  | ---------|--| ------- |-------|-------|--------|--------|
  |ISIC 2020| PSNR  | 22.42  | 23.61|25.03|27.28|32.87|
  | Dataset | SSIM  | 0.7304 |0.7602|0.7941 |0.8203 |0.8249|
  |PH2| PSNR  |22.02|	23.21| 25.73|	28.88	|32.89|
  |  Dataset  | SSIM  |0.7164|	0.7462|	0.7601|	0.7863|	0.9100|
  |Med node| PSNR  | 21.23|	23.5|	24.20| 28.63|	33.49|
  |  Dataset| SSIM  |0.6504|	0.7002|	0.7941|	0.8003| 0.9082|
 ### Qualitative Results
![image](https://user-images.githubusercontent.com/107538530/218392416-8f738bfb-e019-404c-a9b8-6255387745ac.png)


## Comments
  The queries and comments on my codes can be forwarded to v.nirmalaresearch@gmail.com
## Contributors
<!-- Copy-paste in your Readme.md file -->

<a href = "https://github.com/Tanu-N-Prabhu/Python/graphs/contributors">
  <img src = "https://contrib.rocks/image?repo = GitHub_username/repository_name"/>
</a>

Made with [contributors-img](https://contrib.rocks)

 
