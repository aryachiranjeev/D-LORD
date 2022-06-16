# D-LORD

The purpose of this repo is to understand better the paper and do also some experiments with code.
The paper name is "D-LRDO: "

It Comprises of various components:
## Face Detection:
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
For selecting best frames for face recognition, three algorithms have been tested:
1. DWT
   Github link - https://github.com/vitoralbiero/img2pose
   This Detection algorithm took 7.90 ms per frame

2. FQ
   Github link - https://github.com/vitoralbiero/img2pose
   This Detection algorithm took 50.60 ms per frame

3. SER-FIQ
   Github link - https://github.com/vitoralbiero/img2pose
   This Detection algorithm took 518.00 ms per frame
   
It has been observed that SER-FIQ takes less time in selecting good frame for further face recognition and also give better results for Face recognition algorithms discussed in paper.



