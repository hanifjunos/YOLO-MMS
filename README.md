# YOLO-MMS
YOLO-MMS for aerial object detection model based on hybrid feature extractor and improved multiscale prediction

**Setup prerequisites**

This setup is for Windows 10 and NVIDIA-supported GPU.
1.	Install Python 3.7.7, 64 bit
Pip install numpy
2.	Gits installation Version 2.26.2
3.	Cmake installation Version 3.17.2
4.	Visual studio installation VS2019
5.	Updating GPU drives-Install NVIDIA drivers.
6.	CUDA installation- Cuda 10.2.89
7.	CuDnn Installation- Version 7.65 
8.	Opencv installation- Version 4.1.0
Opencv contrib on github
9.	CMake configuration of opencv
10.	Building open CV in Visual studio

**Data preparation**
1.	Locate the image and label file of respective datasets in the ‘data’ folder.
2.	Create test.txt and train.txt files for respective datasets that contain the list name of the images according to their directory. Then, create. names file that contains the list of classes in the dataset. Locate all files in the vedai/visdrone folder.
3.	Create .data files for both datasets and locate in the ‘cfg’ folder. The file contains the following information:

classes= 12
train  = vedai/train.txt  
valid  = vedai/test.txt  
names = vedai/obj.names  
backup = backup/

4.	Locate the YOLO-MMS.cfg file in the ‘cfg’ folder.

**Training & testing**
1.	Training on visdrone dataset

darknet.exe detector train cfg/obj_visdrone.data cfg/YOLO-MMS_visdrone.cfg -map

2.	Testing on visdrone dataset

darknet.exe detector test cfg/obj_visdrone.data cfg/ YOLO-MMS_visdrone.weights -dont_show

3.	Check mAP
   
darknet.exe detector map cfg/obj_visdrone.data cfg/ YOLO-MMS_visdrone.weights -dont_show
