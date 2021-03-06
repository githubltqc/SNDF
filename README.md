# Superpixel-enhanced Deep Neural Forest for Remote Sensing Image Semantic Segmentation
NOTE: The CODE is UNDER maintenance since 13 Oct 2020. Codes and modifications will continue to be updated.

Results for Paper: [Superpixel-enhanced Deep Neural Forest for Remote Sensing Image Semantic Segmentation](https://www.sciencedirect.com/science/article/pii/S0924271619302606)  
![Framework](https://github.com/mi18/SNDF/blob/master/Frameworks.png) 
## Environments
* Python 3.6.2
* Tensorflow 1.6.0
* Numpy 1.13.1
* Opencv-python
* Matplotlib
* Scipy

## Data
*	Download the test image (RGB for Potsdam/IRRG for Vaihingen) and RGB label image (Fully Reference/No Boundary) from ISPRS 2D semantic labelling website.
*	Transfer the RGB label image to the corresponding label image (provided).
                  
|         | Index | R    | G    | B    |
| ------- | ----- | ---- | ---- | ---- |
| Imp     | 0     | 255  | 255  | 255  |
| Build   | 1     | 0    | 0    | 255  |
| Low     | 2     | 0    | 255  | 255  |
| Tree    | 3     | 0    | 255  | 0    |
| Car     | 4     | 255  | 255  | 0    |
| Cluster | 5     | 255  | 0    | 0    |
| Un      | 6     | 0    | 0    | 0    |

*	Rename the testing image and label image.

## Pre-trained Model
*	Download the Pre-trained [resnet_v2_101.ckpt](https://drive.google.com/file/d/1pMixI1wD11TzbOp-QygUPUygzkGrEuYo/view?usp=sharing) and put it into /Code/net/resnet.
*	Download the Pre-trained [model for Vaihingen Dataset](https://drive.google.com/file/d/10V9Qtz8kKMH2uybOzLdLRnT_HTeY-vHb/view?usp=sharing) and put it into /Models/Vaihingen.
* Download the Pre-trained [model for Potsdam Dataset](https://drive.google.com/file/d/10V9Qtz8kKMH2uybOzLdLRnT_HTeY-vHb/view?usp=sharing) and put it into /Models/Potsdam.

## Evaluation
``` python
import predict_potsdam
predict_potsdam.process()

import predict_vaihingen
predict_vaihingen.process()
``` 
* The results include the predict RGB image, the predict Label image and the results.txt for accuracy.
* The whole evaluation process is about 20min.

## Results
|                      | Imp.S.   | Imp.S. |  Build.  |   Build.   | Low.V.   | Low.V. | Tree     | Tree | Car      | Car  | Mean     | Mean     | OA       |
| -------------------- | -------- | ------ | -------- | ---------- | -------- | ------ | -------- | ---- | -------- | ---- | -------- | -------- | -------- |
|                      | F1       | IoU    | F1       | IoU        | F1       | IoU    | F1       | IoU  | F1       | IoU  | F1       | IoU      |          |
| Potsdam              | 93.5     | 87.7   | 96.3     | 93.0       |89.8      | 81.5   |   92.7   | 86.4 | 96.7     | 93.6 |   93.8   |88.4      | 92.1     |
| Vaihingen            | 93.6     | 87.9   | 96.2     | 92.6       |88.0      | 78.6   |   92.6   | 86.3 | 85.3     | 74.4 |   91.1   |83.9      | 92.6     |

## Acknowledgements
Our code is developed based on：

[ssn_superpixels](https://github.com/NVlabs/ssn_superpixels)  
[pytorch_ssn](https://github.com/CYang0515/pytorch_ssn)  
[fully-differentiable-deep-ndf-tf](https://github.com/chrischoy/fully-differentiable-deep-ndf-tf)  
[Neural-Decision-Forests](https://github.com/jingxil/Neural-Decision-Forests)  
[tensorflow-deeplab-v3](https://github.com/rishizek/tensorflow-deeplab-v3)  
[deeplabv3-Tensorflow](https://github.com/ximimiao/deeplabv3-Tensorflow)  

## Cite
@article{Li2020Superpixel,  
  title={Superpixel-enhanced deep neural forest for remote sensing image semantic segmentation},  
  author={Li Mi and Zhenzhong Chen},  
  journal={ISPRS Journal of Photogrammetry and Remote Sensing},  
  volume={159},  
  pages={140-152},  
  year={2020},  
}

