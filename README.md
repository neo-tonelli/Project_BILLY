# Project_BILLY

## Obstacle Detection using <a href="https://pjreddie.com/darknet/yolo/" title="YoloV3">YoloV3</a>. 

Built from AlexeyAB's <a href="https://github.com/AlexeyAB/darknet" title="Darknet">Darknet</a> and Validated by <a href="https://github.com/MiguelARD/DoorDetect-Dataset" title="DoorDetect-Dataset">DoorDetect-Dataset</a>. Custom data set created by downloading images from google images and using <a href="https://github.com/heartexlabs/labelImg" title="labelImg">labelImg</a> tool to create labels used for training. All models trained via transfer learning using the initial weights 'darknet53.conv.74' from <a href="https://pjreddie.com/darknet/yolo/" title="YoloV3">YoloV3</a>. The configuration files can be found here, the final trained weights can be found <a href="https://drive.google.com/drive/folders/1N_Z6B985iYC5AdrLuBfe8XfZSjK0Dq7d?usp=share_link" title="HERE">HERE</a> along with all additional files need to run each model.

## Images
The images used for training the 'custom' model (referred to as V1) were downloaded from google images using a chrome extension to save each image on the results page and classification was done manually via <a href="https://github.com/heartexlabs/labelImg" title="labelImg">labelImg</a> (example shown below). The images used for training the 'BILLY' model (referred to as V2) were downloaded from <a href="https://storage.googleapis.com/openimages/web/index.html" title="Google Open Image Data Set">Google Open Image Data Set</a> using <a href="https://github.com/EscVM/OIDv4_ToolKit" title="OIDv4_ToolKit">OIDv4_ToolKit</a> modified by <a href="https://github.com/theAIGuysCode/OIDv4_ToolKit" title="theAIGuysCode">theAIGuysCode</a>, the classification of these images were  downloaded as part of the google data set.

![alt text](/readme_figures/DoorClassification.png)

## Object Classes and Labels

V1 contained only two classes (0) ***Door*** (1) ***Handle***, the data set comprised of only 69 images (some with multiple instances of both a door and handle - example data below).

V2 contained five classes (0) ***Door*** (1) ***Dog*** (2) ***Cat*** (3) ***Person*** (4) ***doorhandle***, comprised of 1995 images (400 per class except person which was 395). Classes (0)-(3) used <a href="https://storage.googleapis.com/openimages/web/index.html" title="Google Open Image Data Set">Google Open Image Data Set</a> where as class (4) was pulled from <a href="https://universe.roboflow.com/new-workspace-secnu/yolov3-wodvx/dataset/2" title="yolov3-wodvx">yolov3-wodvx</a>.

All labels were formatted in the standard format for <a href="https://pjreddie.com/darknet/yolo/" title="YoloV3">YoloV3</a> where:
* `<object-class>`: integer number of object.
* `<x> <y> <width> <height>`: float values relative to width and height of the image.
* `<x> <y>`: center of the box.

![alt text](/readme_figures/Samples.png)

## Results

All results can be found in the Result folder on the <a href="https://drive.google.com/drive/folders/1N_Z6B985iYC5AdrLuBfe8XfZSjK0Dq7d?usp=share_link" title="Google Drive">Google Drive</a>, below are some examples of detection within photos and videos. This is a good example of how BILLY would detect obstacles in a scene. <a href="https://github.com/MiguelARD/DoorDetect-Dataset" title="DoorDetect-Dataset">DoorDetect-Dataset</a> is provided as a comparison model that was trained for a similar purpose.

Version 1 to 3 from left to right.

![alt text](/readme_figures/SimpleDoor.png) 
![alt text](/readme_figures/AnotherDoor.png) 

### Version 1
![alt text](/readme_figures/results-v1.gif) 

### Version 2
![alt text](/readme_figures/Results-2.gif) 

### <a href="https://github.com/MiguelARD/DoorDetect-Dataset" title="DoorDetect-Dataset">DoorDetect-Dataset</a>
![alt text](/readme_figures/results-v3.gif)

The video above shows the misclassification due to the additional classes that are not relevant to the model used for BILLY.

