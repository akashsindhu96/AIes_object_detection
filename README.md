## Yolov3 object detection with flask and tensorflow 2.0

Yolov3 is an algorithm that uses convolutional neural network to perform object detection. Open source two endpoints each for image and video detections which can be integrate in any application. An example of integration with iOS app is shown in this repo. 

## Features 

1. Two Endpoints (image and Video)
2. Boundary boxes 
3. 80 objects can be classified and detected. 

## Directory Structure

    .
    ├── doc                     # Canvas documents, presentations
    ├── src                     # Source files 
    ├── pubs                    # Documentation files 
    │   ├── figs                # Figures
    └── README.md

## Getting Started  

### Pip  
Tensorflow CPU  
`pip install -r requirements.txt`


### Download official pre-trained weights for COCO dataset  
yolov3 For Windows:    
You can download weights by clicking here [here](https://pjreddie.com/media/files/yolov3.weights)

### Saving your weights as Tensorflow model  
Now you have to load the models and convert them to tensorflow checkpoint files.


yolov3  
`python load_weights.py`  

### Running flask web app for two API endpoints 

`python app.py`

This will start a web server on localhost. To check the detection open the `Postman`, select body > form-data > file and upload image. 

endpoints  
`http://localhost:5000/image`  
`http://localhost:5000/detections`  


### Detections API (http://localhost:5000/detections)  
This route takes in the image input and returns a JSON response with all the detections found within each image (classes found within the images and the associated confidence)

### Image API (http://localhost:5000/image)  
This route takes in the image input and returns the image response with all the detections found within the image and their bounding boxes. 


### To run the video  
Video can only be run through this command so far.  
`python detect_video.py --video path-to-video`

### iOS Application 
To run the iOS application run the .xcodeproj found in src/AIes-Ios./Swift. In order for the application to run, the application must be in lanscape mode and must have the URL in line #778 updated according to the service running. 

### Demo 
* [Demo for video object detection](https://www.youtube.com/watch?v=RWQoXcmKj4M)
* [Demo for picture object detection](https://www.youtube.com/watch?v=IOtumq42sCM)

### Authors 
* Akash Sindhu  
* Maninder Singh   
* Tommy Chivaz  
* Jiawei Zhang   

### Acknowledgments

* [Yolov3 TensorFlow 2 Amazing Implementation](https://github.com/zzh8829/yolov3-tf2)  
* [Another Yolov3 TensorFlow 2](https://github.com/heartkilla/yolo-v3)   
* [Yolo v3 official paper](https://arxiv.org/abs/1804.02767)  
* [A Tensorflow Slim implementation](https://github.com/mystic123/tensorflow-yolo-v3) 
* [AVCam Building a Camera App](https://developer.apple.com/documentation/avfoundation/cameras_and_media_capture/avcam_building_a_camera_app) 
