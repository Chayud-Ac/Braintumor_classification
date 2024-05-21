# Brain Tumor Classification using Transfer Learning

## Developing the Model

This repository focuses on the development of the deep learning model using transfer learning for brain tumor classification The primary goal is to create an accurate and efficient model that can classify brain tumors from medical images. The classes or labels of brain tumor are

- glioma - usually grow in the brain, but can also form in the spinal cord. Gliomas are malignant (cancerous), but some can be very slow growing.
- meniningioma - the most common type of primary brain tumor. These tumors originate in the meninges, which are the outer three layers of tissue between the skull and the brain that cover and protect the brain just under the skull.
- notumor - compose of normal function without any tumor
- pituitary - Pituitary tumors are tumors that form in the pituitary gland near the brain

## Dataset

The model is trained on a dataset of brain tumor images. Obtain form open sourse platform name Kaggle
link -> https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset/data

Originally there are two seperate dataset training and testing. This project is futher seperate the training set into training and validation as we will need validation set to tracking the training process. The testing set will use as model evaluation in the final process after training is done.

## Setup

You can install and work in wsl to allow tensorflow-gpu.

### Create and activate conda environment using environment.yml (This provided all library using in this project)

```bash
conda env create -f environment.yml
conda activate classification  # Double check the name in environment.yml

```

## Precess overview

- Data_analysing - This mainly focusing on virtualizing the dataset, analyze the bit depth of the image , distribution of labels

- Data_preprocessing_and_training - This focus of developing preprocess pipeline and training pipeline. Preprocessing will compose of normalize the image or rescaling the image in range of 0-1 as well as data augmentation to prevent model overfit and generate more diverse training set. For training pipeline we use multiple base model in this project including Inception V3 , Xception , InceptionResNetV2.

- Model_evaluation - evaluate the model base on testing set using matrix like accuracy , loss , f1 score , confusion matrix.

## Summary

Model xception
Test Loss: 0.1648
Test Accuracy: 0.9542
F1 Score: 0.9541

Model InceptionV3
Test Loss: 0.1226
Test Accuracy: 0.9611
F1 Score: 0.9610

## future scope

fine tuning the model with different type of data augmentation or different value of hyperparameter. The save model can be futher use to generate heatmap to identify the region of the image that influence on the model prediction.
