Project Overview : 

DiagramVision is a computer vision project designed to automatically detect and identify common components in flowchart diagrams.

The system uses an object detection model to recognize flowchart elements and display their locations using bounding boxes, class labels, and confidence scores.

The project represents an initial step toward intelligent diagram-understanding systems that can transform visual flowcharts into structured, machine-readable information.

The system currently detects four flowchart components:

Process
Decision
Start/Stop
Input/Output  

Problem Description : 

Flowcharts are widely used in software development, system design, and graduation projects to represent processes and system logic. However, the information contained in flowcharts is mainly visual and normally requires manual interpretation.

Automatically detecting flowchart components is an important first step toward converting visual diagrams into structured information that can later be analysed by intelligent systems.

The purpose of DiagramVision is therefore to develop a computer vision system capable of automatically identifying and locating common flowchart components from diagram images.

Expected Output: 

Flowchart Image → Detected Components → Bounding Boxes + Class Labels + Confidence Scores

Dataset & Model Used :   

A custom dataset containing 51 original flowchart images was collected for this project.

The images were manually annotated using Roboflow, with bounding boxes assigned to the four target component classes.

The dataset was divided into training, validation, and testing sets. Before training, the images were resized to 512 × 512 pixels, and suitable data augmentation techniques were applied to increase variation in the training data.

The project uses a pretrained YOLO11n object detection model. Transfer learning was used to fine-tune the pretrained model on the custom flowchart dataset.

Computer Vision Task: Object Detection
Model: YOLO11n
Input Size: 512 × 512
Training Epochs: 30

Property 	Value
# images	51
Dataset	Custom dataset
Task of Computer Vision 	Object Detection 
Classes 	4 classes { start_end, Process, input_output, Decision}
Annotation Tool 	Roboflow ( manual)




Workflow / Architecture

Flowchart Images
       ↓
Manual Annotation using Roboflow
       ↓
Dataset Split
       ↓
Preprocessing & Data Augmentation
       ↓
Pretrained YOLO11n
       ↓
Transfer Learning / Fine-Tuning
       ↓
Model Evaluation
       ↓
New Flowchart Image
       ↓
Component Detection
       ↓
Bounding Boxes + Classes + Confidence Scores
       ↓
Component Counting
       ↓
DiagramVision Output


Results & Evaluation

The trained model was evaluated on the validation dataset using mAP@50 and mAP@50–95.

Class	       mAP@50	      mAP@50–95
Decision	55.1%	      40.6%
Process	        18.1%	      9.9%
Input/Output	52.5%	      31.5%
Start/Stop	85.5%	      54.4%
Overall	        52.8%	      34.1%


The Start/Stop class achieved the highest detection performance, with an mAP@50 of 85.5%. The Process class was the most challenging, achieving an mAP@50 of 18.1%.

The results demonstrate that the model was able to learn and detect flowchart components, although its performance varied considerably between classes. The relatively small dataset and limited examples for some classes may have affected the model's ability to generalise.

A confusion matrix, a successful prediction, and a failure case were also analysed to better understand the model's behaviour.

Technologies Used

Python
Google Colab
Ultralytics YOLO11
Roboflow
PyTorch
OpenCV
Matplotlib
GitHub










SDAIA Academy https://github.com/SDAIAAcademy




