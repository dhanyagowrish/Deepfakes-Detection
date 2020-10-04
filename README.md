# Deepfakes Detect
A convolutional neural network to detect if a video is a deepfake or not  

## Challenge
[Kaggle Deepfakes Detection Challenge](https://www.kaggle.com/c/deepfake-detection-challenge)  
  
### Dataset  
The dataset contained 875 videos from the Kaggle Deepfakes Challenge dataset. The proportion of real and fake videos in our dataset was nearly equal. This was split in an 80:20 ratio for train and validation data.  
  
Training Dataset: 700 videos  
Validation Dataset: 175 videos  

## Solution  
A frame-based approach was used. Each video is split into frames and faces are detected within these. ResNet-50 was finetuned to detect with a probability if a frame was a deepfake or not.  

### Face Detection  
MTCNN detector was used to detect faces within frames of the video  

### Model  
Pre-trained ResNet50 is used. The weights are un-freezed and finetuned for the deepfakes detection task. The model was trained for 50 epochs.  
Loss Function : Cross entropy loss  
Optimizer: Stochastic graident descent  
Scheduler:  Exponential  

### Results  
Our model achieved an accuracy of 85.8% and a validation loss of 0.34.  

### In this repo  
data_pre_processing.ipynb - splitting video into frames, identifying faces, loading frames/videos into appropriate directories  
  
model.ipynb - finetuning ResNet50 model  
  
testing.ipynb - functions for testing the trained model

