# D-LORD: DYSL-AI Database for Low-Resolution Disguised Face Recognition

D-LORD is a large-scale dataset that aims at strengthening the research on low-resolution disguised face detection. It leverages surveillance videos where the subjects may or may not be wearing disguise accessories, such as hats, beards and mustaches, sunglasses, and face masks.
 
![collage_page-0001](https://user-images.githubusercontent.com/31439731/174141468-d82f1ba6-d52a-40e6-861d-ff073a0613ba.jpg)

We benchmark the performance of various face detection, face recognition, face restoration, and frame selection algorithms on the proposed D-LORD.

## Face Detection
Face Detection is performed on the video frames in-order to extract the region of interest. In this study, we utilize three face detection algorithms:
1. YoloV5Face
   Github link - https://github.com/deepcam-cn/yolov5-face
   
   This Detection algorithm took 24.20 ms per frame
   
2. RetinaFace
   Github link - https://github.com/elliottzheng/face-detection
   
   This Detection algorithm took 308.45 ms per frame
 
3. Img2Pose
   Github link - https://github.com/vitoralbiero/img2pose
   
   This Detection algorithm took 78.02 ms per frame
   
It has been observed that YoloV5Face yields greater Mean IOU(mIOU) for all distances, i.e. 5m (96%), 7m (92%), 10m (89%), and 15m (85%). This performance is better as compared to other Face detection algorithms.
   
## Frame Selection
To select the best frames for face recognition, we divide the surveillance videos into four parts based on the subject's distances from the camera (5m, 7m, 10m, and 15m). From each part, we select three best frames using three frame selection algorithms:
1. DWT
   Github link - https://ieeexplore.ieee.org/document/7850956
   
   This algorithm took 7.90 ms per frame

2. FQ
   Github link - https://github.com/uam-biometrics/FaceQnet
   
   This algorithm took 50.60 ms per frame

3. SER-FIQ
   Github link - https://github.com/pterhoer/FaceImageQuality
   
   This algorithm took 518.00 ms per frame
   
From our experiments, SER-FIQ proves to be the best frame selection algorithm, but its per frame inference time is 65 times higher than the DWT-based method. SER-FIQ yields 79.35% GAR at 5m and 49.45% GAR at 15m. Further results and bar plots are shown in the paper.


## Face Restoration
Face restoration techniques are used to improve the quality of low-resolution facial images:
1. GFP-GAN
   Github link - https://github.com/TencentARC/GFPGAN
   
   This algorithm took 11.00 ms per frame

2. PSFR-GAN
   Github link - https://github.com/chaofengc/PSFRGAN
   
   This algorithm took 100.00 ms per frame

3. Real-ESRGAN
   Github link - https://github.com/xinntao/Real-ESRGAN
   
   This algorithm took 52.20 ms per frame
   
It is observed that GFP-GAN takes less time for super resolution of the faces. 

## Face Recognition
The three state-of-the-art Face Recognition algorithms have been taken into consideration for performing the experiments:  
1. ArcFace 
   Github link - https://github.com/deepinsight/insightface/tree/master/recognition/arcface_torch
   
   This algorithm took 4.21 ms per frame

2. LightCNN
   Github link - https://github.com/AlfredXiangWu/LightCNN
   
   This algorithm took 67.00 ms per frame

3. ElasticFace
   Github link - https://github.com/fdbtrs/ElasticFace
   
   This algorithm took 58.64 ms per frame
   
It has been observed that ElasticFace performs better at 5m and 7m distances, while ArcFace performs better for distances more than 10m and 15m. The performance of LightCNN is significantly lower than the other recognition models. 

The detailed results are discussed in the paper.

## Downscaled LR Vs Real LR
We provide some samples of downscaled LR and real LR images in various resolutions. It can be observed that there is a significant difference in the visual quality of real and downscaled images.
![LR](https://user-images.githubusercontent.com/31439731/186117319-99936363-23db-4bfa-9f2c-194304192663.jpg)

## Datasheet for D-LORD

