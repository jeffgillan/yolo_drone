## YOLO Object Detection on MP4 Videos

<img src="/hiker_identify.gif" width=600>

### Intro
This python code (yolo_drone_slice.ipynb) is meant to detect objects in drone-based mp4 video using the YOLO object detection vision model. Users supply an aerial mp4 video and receive an output mp4 with bounding box prediction embedded (per frame) throughout the video. 

This implementation partitions the frame into chips (aka slices) sized 640x640px and predicts across each chip. This ensures high-resolution prediction across the whole image. Good for detecting small objects across large formats like 4k video. 


### Object Classes
The model can identity 12 object classes: 0 = light vehicle; 1 = person; 2 = building; 3 = Utility pole; 4 = boat; 5 = bike; 6 = container; 7 = truck; 8 = gastank; 10 = digger (construction equipment); 11 = solar panels; 12 = bus.


### Fine-tuned Model Weights
The [fine-tuned model](https://huggingface.co/StephanST/WALDO30/resolve/main/WALDO30_yolov8m_640x640.pt?download=true) used here is trained from the [YOLOv8 model](https://yolov8.com/) object detection model. It trains and predicts on RGB image size 640x640.  

### Training Dataset
The [Waldo](https://huggingface.co/StephanST/WALDO30) dataset is the developers private dataset of synthetic and "augmented" / semi-synthetic data. It is not currently public.

 
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

