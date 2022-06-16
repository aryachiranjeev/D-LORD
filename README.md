# D-LORD

The purpose of this repo is to understand better the paper and do also some experiments with code.
The paper name is "D-LORD: DYSL-AI Database for Low-Resolution Disguised Face Recognition"
We provides baseline results on our proposed datasets for various components:
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
   
It has been observed that YoloV5Face greater Mean IOU(mIOU) for all distances 5m(96%), 7m(92%), 10m(89%), 15m(85%) as compared to other Face detction algorithms. 
   
## Frame Selection
For selecting best frames for face recognition, we divided the video into four parts based on the distances upto 5m, 7m, 10m, 15m. From each part we select 3 frames on the bases of three frame selection algorithms that have been used:
1. DWT
   Github link - 
   This algorithm took 7.90 ms per frame

2. FQ
   Github link - 
   This algorithm took 50.60 ms per frame

3. SER-FIQ
   Github link - 
   This algorithm took 518.00 ms per frame
   
It has been observed that SER-FIQ takes a lot of time in selecting good frame for further face recognition but yet it yields the best performance for Face recognition algorithms discussed in THE paper. SER-FIQ yields 79.35% GAR at 5m and 49.45% GAR at 15m. Further results and bar plots are shown in the paper D-LORD.



## Face Restoration
Face restoration techniques have been used as it lead to significant improvement in Face Verification performance. Three Face Restoration algorithms used are:
1. GFP-GAN
   Github link - https://github.com/TencentARC/GFPGAN
   This algorithm took 11.00 ms per frame

2. PSFR-GAN
   Github link - https://github.com/chaofengc/PSFRGAN
   This algorithm took 100.00 ms per frame

3. Real-ESRGAN
   Github link - https://github.com/xinntao/Real-ESRGAN
   This algorithm took 52.20 ms per frame
   
It has been observed that GFP-GAN takes less time for super resolution of the faces. 

## Face Verification
Three state-of-the-art Face verification techniques have been taken into consideration.  
1. ArcFace 
   Github link - https://github.com/deepinsight/insightface/tree/master/recognition/arcface_torch
   This algorithm took 4.21 ms per frame

2. LightCNN
   Github link - https://github.com/AlfredXiangWu/LightCNN
   This algorithm took 67.00 ms per frame

3. ElasticFace
   Github link - https://github.com/fdbtrs/ElasticFace
   This algorithm took 58.64 ms per frame
   
It has been observed that Elastic Face performs better upto 5m and 7m distances and ArcFace perform better for distances more than 10m and upto 15m. Whereas LightCNN perform worst for all four distances.

The detailed results are discussed in the paper D-LORD.


