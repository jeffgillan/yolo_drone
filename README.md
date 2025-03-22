## YOLO Object Detection on MP4 Videos
### Description
<img src="/hiker_identify.gif" width=600>

This python code (yolo_drone_slice.ipynb) is meant to detect objects in drone-based mp4 video using the YOLO object detection vision model. Users supply an aerial mp4 video and receive an output mp4 with bounding box prediction embedded (per frame) throughout the video. 

### Task
Object detection with bounding boxes

### Object Classes
The model can identity 12 object classes: 0 = light vehicle; 1 = person; 2 = building; 3 = Utility pole; 4 = boat; 5 = bike; 6 = container; 7 = truck; 8 = gastank; 10 = digger (construction equipment); 11 = solar panels; 12 = bus.

### Fine-tuned Model 
The model used is the [YOLOv8 model](https://yolov8.com/) that has been fine tuned on the [WALDO dataset](https://huggingface.co/StephanST/WALDO30). 


### Training Dataset
The [Waldo](https://huggingface.co/StephanST/WALDO30) daaset is the developers private dataset of synthetic and "augmented" / semi-synthetic data. It is not currently public.

This implimentation will take the input video resolution and 'slice' it into smaller image squares (e.g., 640x640 pixels) to do the predictions. Slice is the same thing as crop or tile. 

User inputs include the video path, the output path, the model to use, the classes to detect, and the confidence threshold.

The model used is the YOLOv8 model that has been fine tuned on the [WALDO dataset](https://huggingface.co/StephanST/WALDO30). The dataset itself is not public, but the weights of this fine tuned model are available on Hugging Face. WALDO has been trained to identify 12 different objects.  

The WALDO fine tuned model is available on Hugging Face [here](https://huggingface.co/StephanST/WALDO30/resolve/main/WALDO30_yolov8m_640x640.pt?download=true). Download the `pt` file to your local machine. 

Having access to a GPU will significantly increase the speed of the predictions.

<br>
<br>

## Run locally

Download this repository to your local computer

`git clone git@github.com:jeffgillan/yolo_drone.git`

<br>
<br>

Create a new environment with the provided env.yml

`conda env create --file yolo_drone_slice_env.yml`


<br>
<br>

Open the file `yolo_drone_slice.ipynb` in VScode 

Select the python kernel to be `yolo_drone_slice`

