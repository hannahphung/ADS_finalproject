# ADS_finalproject
* Project Member : Yen Le, Hannah Phung and Manjiri Bhandarwar
* Project Goal : Skin disease detection by images using Deep Learning 

# Project Description

## Project Flow

## Dataset Preprocessing

Dataset: [HAM10000](https://www.kaggle.com/datasets/kmader/skin-cancer-mnist-ham10000)

* Handling Metadata:
  * Cleaned missing values (e.g. imputed null age values with mean)
  * Removed rows with age 0 or 'unknown' sex
  * Minor reduction in observations for specific classes
  * Categorically encoded lesion types as 'cell type idx' (target)
* Image Processing: resized to 125x100 pixels, normalized by dividing by 255 and standardization applied on training data
* Handling Data Imbalance: Avoided random oversampling due to huge class imbalance (potential overfitting issues)
* Data Split: Split dataset: 80-20 train-test, further split train into 90-10 train-validation
* Implemented data augmentation using ImageDataGenerator
  * Random rotation (0-10 degrees)
  * Horizontal and vertical shifts
  * Random zoom (factor 0.1)
  * Random flipping of images

## Project Framework / Model Architectures
![alt text](https://github.com/hannahphung/ADS_finalproject/blob/main/img/method.png)
Baseline models: Pretrained DenseNet201 and ResNet50, 95 Base layers freezed and fine-tuned with HAM10000 dataset. Also used learning rate scheduler: ReduceLRONPlateau + Exponential decay and early Stopping
![alt text](https://github.com/hannahphung/ADS_finalproject/blob/main/img/res.png)
![alt text](https://github.com/hannahphung/ADS_finalproject/blob/main/img/dense.png)


# Code Details


# Results and Observations

## Milestone 2

![alt text](https://github.com/hannahphung/ADS_finalproject/blob/main/img/download-5.png)
![alt text](https://github.com/hannahphung/ADS_finalproject/blob/main/img/download-6.png)
![alt text](https://github.com/hannahphung/ADS_finalproject/blob/main/img/download-7.png)

## Milestone 3

![alt text](https://github.com/hannahphung/ADS_finalproject/blob/main/img/download-1.png)
![alt text](https://github.com/hannahphung/ADS_finalproject/blob/main/img/f1scorem3.png)



## Discussion/Insights



# References




