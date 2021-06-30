# Player-and-Football-detection-using-YOLOv4
This repository contains the codes and datasets to perform players and football detection on a streamed football match video. For this task, we used darknet implementation of yolov4 object detector. Here we trained the model for three different types of dataset.

**Demo**  
![video](https://github.com/Decepticons-06/Player-and-Football-detection/blob/main/ezgif.com-gif-maker.gif)

## How to use ?
First, collect the datasets from my <a href="https://drive.google.com/drive/folders/1C_SeAv8oSMjIDs87oqBML6hW3hzrgkBn?usp=sharing" target="_blank">Google Drive link</a>.
The drive link contains three datasets ISSIA-CNR dataset, SPD-BMV-2017 dataset and MOUNSIF dataset.
Then do data preprocessing for three types of datsets :
1. Move to the Directory  
      `cd Player-and-Football-detection`    
2. Data-preprocessing for ISSIA dataset  
      `python3 ISSIA-CNR_data_cleaning.py`
3. Data-preprocessing for SPD dataset  
      `python3 SPD_data_cleaning.py`
4. Data-preprocessing for MOUNSIF dataset  
      `python3 MOUNSIF_data_cleaning.py`
5. To merge the three datasets and create train.txt and test.txt files  
      `python3 merge_split_datsets.py`

Two directories named **images** and **labels** will be created. **images** contains .jpg image files and **labels** contains .txt annotation files corresponding to each image.
The .txt files in **labels** contains object annotations in this format:  
***(class_id, norm_x_top_left, norm_y_top_left, norm_width, norm_hight)***

Each of train.txt and test.txt file contains image paths :  
```csv
      data/obj/1391.jpg  
      data/obj/4827.jpg  
      data/obj/3723.jpg  
      data/obj/4316.jpg  
      data/obj/2917.jpg  
      data/obj/4465.jpg  
      data/obj/3594.jpg...  
```      
  
To train and make prediction on test images, please follow the ipynb notebook.

**Inference on image of ISSIA dataset**
![issia_prediction](https://github.com/Decepticons-06/Player-and-Football-detection/blob/main/results/issia_predictions.jpg)


**Inference on image of SPD dataset**
![spd_prediction](https://github.com/Decepticons-06/Player-and-Football-detection/blob/main/results/spd_predictions.jpg)


**Inference on image of MOUNSIF dataset**
![mounsif_prediction](https://github.com/Decepticons-06/Player-and-Football-detection/blob/main/results/mounsif_predictions.jpg)



For more information regarding the methodology and evaluation metrics, please refer to the attached pdf file.

**References :**  
1. YOLOv4 paper (<a href="https://arxiv.org/abs/2004.10934" target="_blank">link</a>)  
2. AlexeyAB/darknet (<a href="https://https://github.com/AlexeyAB/darknet" target="_blank">link</a>)
