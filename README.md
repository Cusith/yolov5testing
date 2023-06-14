# yolov5testing
Demonstration and documentation of yolov5 capabilities

### Outside Resources
This repository holds the documentation and testing of running yolov5. 
yolov5 was cloned from this [repository](https://github.com/ultralytics/yolov5).  
  
### Testing information
Weights used were yolov5x.pt and default weights.  
  
A variety of tests were conducted to show the accuracy of yolov5's model. Numerous iterations of the test have been run using altered weights and thresholds. Input media was varied between live source webcams and downloaded videos. 

### Testing Environment/Equipment  
#### Testing Equipment  
Processor	Intel(R) Core(TM) i7-9750H CPU @ 2.60GHz   2.59 GHz  
Installed RAM	24.0 GB (23.9 GB usable)  
System type	64-bit operating system, x64-based processor  
System Model	ROG Strix G531GT_G531GT  
Graphics Processor NVIDIA GeForce GTX 1650 4GB VRAM  
Webcam NexiGo N980P 1080P 60FPS  
  
#### Testing Environment  
Living room table with an assortment of objects on table and in background.  
Hayward Public Library 3rd floor window to the outside.  
  
### Setup  
1. Install [miniconda](https://docs.conda.io/en/latest/miniconda.html) as environment to run the model.  
2. Open up miniconda and use the command: **_conda install pytorch torchvision torchaudio pytorch-cuda=11.7 -c pytorch -c nvidia_**  
3. Clone yolov5 from it's repository with the command: **_git clone https://github.com/ultralytics/yolov5_**
4. Retarget the directory to the yolov5 clone with the command: **_cd yolov5/_**  
5. If step 2 went well it should have installed **_pip_**, if **_pip_** was not installed run this command: **_conda install pip_**, run this command to install the rest of the requirements documented in the yolov5 repository: **_pip install -r requirements.txt_**  

### Live Webcam Setup  
1. Make sure you have a webcam plugged into the system, if you only have one the default **_source_** will be 0.  
2. Type in the command: **_python detect.py --source 0_**, this will find the default or first webcam registered on your system and proceed to start the yolov5 model.
3. Once the model is done fusing layers it will open up a preview window showing the webcam feed and any detected objects will be marked with their category and confidence values. 
4. Apply additional weights and thresholds as needed. 

### Downloaded Video Setup  
1. Since you do not need a webcam for this the **_source_** will instead be a directory to the file of your choosing within your particular system. Due to differences in file systems some directories may appear different, this setup is assuming a Windows PC.
2. The new command to use is: **_python detect.py --weights yolov5x.pt --data C:\Users\username\Desktop\models\video.mp4_**, the command is the same for the most part until you add model weights which is what **_--weights yolov5x.pt_** is for, we replace the **_--source_** with **_--data_** and follow up with the directory to the file of our choosing.
3. Once you run that command it will bring up the the command line interface that the yolov5 model was running on and display all the detected objects in category and quantity. If you want to see the chosen file with realtime detection add in this command segment at the end: **_--view-img_**.  
4. You can modify the object detection rates and particular thresholds using **_--conf-thres_** and **_-iou-thres_** you simply need to put a rating next to both of them to enable a minimum threshold regarding their particular weights. **_--conf-thres 0.9_** raises the minimum detection confidence to 90% so that the yolov5 model will only give you a positive reading if it is 90% sure that the object is recognized properly. Similarly **_-iou-thres 0.9_** will alter the spacing between objects and how much can overlap when beind detected. You can change those threshold weights at any time to alter the accuracy of the model.
