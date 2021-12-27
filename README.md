# AMLS_21-22_SN18014580

## Introduction to the assignment

This is the GitHub repository created by *STUDENT NUMBER 18014580* for the 2021/22 ELEC0134 Applied Machine Learning Systems final coding assignment. This repository is made up of 3 files/scripts that are used for Task A and B respectively. 

For this assignment we are given an initial data set containing 3000 512x512 images of MRI scans for brain tumours and are also given a `.csv` file containing labels indicating the type of tumour for each of the 3000 images. We are later given a similar unseen testing set, only made available a week before the deadline for validation purposes.

In the assignment, we are required to build classifiers which perform image classification on the datasets given. These classification tasks can be split into Tasks A and B as described below:

* In Task A, we are required to to determine from the image if there is a tumour present or not, hence this is a binary classification problem.
* In Task B, we are required to determine the type of the tumour if one is present, rather than just determining if a tumour is present or not. Hence, this is a multiclass classification problem.

## Repository structure

This repositiory is made of 3 main files/scripts used for Tasks A and B respectively. The detailed breakdown of these main files is given below:

* `Task A using Logistic Regression.ipynb` is used to run the binary classifier for Task A using the Logistic Regression model. This trains a Logistic Regression model using the dataset uploaded and then tests it using both the dataset uploaded and the new testing set uploaded a week before the deadline. The testing outputs classification reports and confusion matrices. Hyperparameter tuning is also conducted to improve accuracy scores.
* `Task A using SVM.ipynb`is used to run the binary classifier for Task A using the Support Vector Machine (SVM) model. This trains 3 SVMs (3 different kernel types) using the dataset uploaded and then tests it using both the dataset uploaded and the new testing set uploaded a week before the deadline. The testing outputs classification reports and confusion matrices. Hyperparameter tuning is also conducted to improve accuracy scores and find a final SVM model to use with optimised parameters.
* `Task B using SVM.ipynb` is used to run the multiclass classifier for Task B using the Support Vector Machine (SVM) model. This trains 6 SVMs (3 different kernel types two times each (once using a one-vs-rest approach and once using a one-vs-one approach)). The models are trained using the dataset uploaded and then tested using both the dataset uploaded and the new testing set uploaded a week before the deadline. The testing outputs classification reports and confusion matrices. Hyperparameter tuning is also conducted to improve accuracy scores and find a final SVM model to use with optimised parameters.

A breakdown of the other folders and files in the repository is also given below:

* `READme.md` is this file and is used to give general information about the assignment and submission package including file structure, packages required and instructions on how to run.
* `dataset` is the folder containing the original dataset used for both training and testing. It contains 3000 512x12 MRI images of brain scans and a `.csv` file organising these images into 4 classes of tumours: no tumour, pituitary tumour, glioma tumour and meningioma tumour. 
* `test` is the folder uploaded a week before the deadline containing data solely for testing and validation. It is a separated test set with 200 512x512 MRI images of brain cans and a `.csv` file organising them into the same four classes as before. This is separated from the other data and is used to examine for overfitting.
* `.ipynb_checkpoints` contains checkpoints for our files when they are saved on Jupyter Notebook.


## Packages required

Many of the scripts require the same packages and in this section, we highlight each of the packages.

* `pandas` is required ...

## How to run the code 

## Other special notes and instructions

Repository created by student number 18014580 for the 2021-22 Applied Machine Learning Systems (MLS-1) assignment.
