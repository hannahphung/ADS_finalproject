# ADS_finalproject
* Project Member : Yen Le, Hannah Phung and Manjiri Bhandarwar
* Project Goal : Skin disease detection by images using Deep Learning 

# Project Description

## Project Flow
![alt text](https://github.com/hannahphung/ADS_finalproject/blob/main/img/method.png)

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
**Baseline models:** Pretrained DenseNet201 and ResNet50, 95 Base layers freezed and fine-tuned with HAM10000 dataset. Also used learning rate scheduler: ReduceLRONPlateau + Exponential decay and early Stopping
![alt text](https://github.com/hannahphung/ADS_finalproject/blob/main/img/res.png)
![alt text](https://github.com/hannahphung/ADS_finalproject/blob/main/img/dense.png)
Build on top of baseline model by adding other features to help with performance and avoid overfitting: Data Augmentation, Input Normalization, Batch Normalization, and Dropout

Constructing more complex ensemble models 

**Average Ensemble:** 
![alt text](https://github.com/hannahphung/ADS_finalproject/blob/main/img/average_ensemble.png)

**Classes that are usually misclassified as each other:**
![alt text](https://github.com/hannahphung/ADS_finalproject/blob/main/img/class12.png)
![alt text](https://github.com/hannahphung/ADS_finalproject/blob/main/img/class36.png)

**Hierarchical Ensemble:** 
- To deal with data imbalance, each classifier focuses on classes or combinations of classes that have comparable size. For example, classifier 1 distinguishes between class 0 (around 66% of the dataset) and the remaining 6 classes
- The final stage of the pipeline focuses on pairs of classes (class 1 vs 2 and class 3 vs 6)  that are usually mistaken for each other in the single model case. 
![alt text](https://github.com/hannahphung/ADS_finalproject/blob/main/img/hierachical.png)

**Multimodal approach:** 
Multimodal approach incorporate metadata including age, sex, and localization (i.e. where on the body the disease appear)
![alt text](https://github.com/hannahphung/ADS_finalproject/blob/main/img/multimodal.png)

**Using the best model to test on secondary dataset:** 

The best model is multimodal with DenseNet201
![alt text](https://github.com/hannahphung/ADS_finalproject/blob/main/img/secondary_data.png)

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




