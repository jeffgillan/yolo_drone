## YOLO Object Detection on MP4 Videos

<img src="/hiker_identify.gif" width=600>

### Intro
This python code (yolo_drone_slice.ipynb) is meant to detect objects in drone-based mp4 video using the YOLO object detection vision model. Users supply an aerial mp4 video and receive an output mp4 with bounding box prediction embedded (per frame) throughout the video. 

This implementation partitions the frame into chips (aka slices) sized 640x640px and predicts across each chip. This ensures high-resolution prediction across the whole image. Good for detecting small objects across large formats like 4k video. 

User inputs include the video path, the output path, the model to use, the classes to detect, and the confidence threshold.

### Object Classes
The WALDO fine-tuned model has been trained to identify 12 different objects. 0 = LightVehicle, 1 = Person, 2 = Building, 3 = UPole, 4 = Boat, 5 = Bike, 6 = Container, 7 = Truck, 8 = Gastank, 10 = Digger, 11 = SolarPanels, 12 = Bus


### Fine-tuned Model Weights
The [fine-tuned model](https://huggingface.co/StephanST/WALDO30/resolve/main/WALDO30_yolov8m_640x640.pt?download=true) used here is trained from the [YOLOv8 model](https://yolov8.com/) object detection model. It trains and predicts on RGB image size 640x640.  

### Training Dataset
The [Waldo](https://huggingface.co/StephanST/WALDO30) dataset is the developers private dataset of synthetic and "augmented" / semi-synthetic data. It is not currently public.

### Make you own fine-tuned model 
The jupyter notebook (yolo_drone_slice.ipynb) also includes code to train(fine-tune) the WALDO model based on your labels. If done well, this can significantly improve object detection in your video compared with the WALDO model. Your labeled dataset hould be in the YOLOv8 format, which includes a .yaml file with the class names and a folder with images and labels. I recommend using Roboflow or Labelstudio to label your images and export them in the YOLOv8 format. The labels (classes and order) should be exactly the same as the WALDO dataset.

['LightVehicle', 'Person', 'Building', 'UPole', 'Boat', 'Bike', 'Container', 'Truck', 'Gastank', 'Digger', 'SolarPanels', 'Bus']

<br>
<br>

## Run locally

Download this repository to your local computer

`git clone git@github.com:jeffgillan/yolo_drone.git`

<br>
<br>

Download the model weights [here on huggingface](https://huggingface.co/StephanST/WALDO30/resolve/main/WALDO30_yolov8m_640x640.pt?download=true).

<br>
<br>

Create a new environment with the provided env.yml

`conda env create --file yolo_drone_slice_env.yml`


<br>
<br>

Open the file `yolo_drone_slice.ipynb` in VScode or a code editor of your choice that run jupyter.

<br>
<br>

Select the python kernel to be `yolo_drone_slice`

<br>
<br>

Having access to a GPU will significantly increase the speed of the predictions.

