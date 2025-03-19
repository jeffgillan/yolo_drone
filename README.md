## YOLO Object Detection on MP4 Videos

<img src="/hiker_identify.gif" width=600>

This python code (yolo_drone_slice.ipynb) will do object detection on mp4 videos using the YOLO object detection vision model. The model will try to predict and put bounding boxes on each frame of the video. The output is a new mp4 video with bouding boxes embedded in the video.

This implimentation will take the input video resolution and 'slice' it into smaller image squares (e.g., 640x640 pixels) to do the predictions. Slice is the same thing as crop or tile. 

User inputs include the video path, the output path, the model to use, the classes to detect, and the confidence threshold.

The model used is the YOLOv8 model that has been fine tuned on the [WALDO dataset](https://huggingface.co/StephanST/WALDO30). The dataset itself is not public, but the weights of this fine tuned model are available on Hugging Face. WALDO has been trained to identify 12 different objects. 0 = light vehicle; 1 = person; 2 = building; 3 = Utility pole; 4 = boat; 5 = bike; 6 = container; 7 = truck; 8 = gastank; 10 = digger (construction equipment); 11 = solar panels; 12 = bus. 

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

