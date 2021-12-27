# AMLS_21-22_SN18014580

## Introduction to the assignment

This is the GitHub repository created by **STUDENT NUMBER 18014580** for the 2021/22 ELEC0134 Applied Machine Learning Systems final coding assignment. This repository is made up of 3 files/scripts that are used for Task A and B respectively. 

For this assignment we are given an initial data set containing 3000 512x512 images of MRI scans for brain tumours and are also given a `.csv` file containing labels indicating the type of tumour for each of the 3000 images. We are later given a similar unseen testing set, only made available a week before the deadline for validation purposes.

In the assignment, we are required to build classifiers which perform image classification on the datasets given. These classification tasks can be split into Tasks A and B as described below:

* In Task A, we are required to to determine from the image if there is a tumour present or not, hence this is a binary classification problem.
* In Task B, we are required to determine the type of the tumour if one is present, rather than just determining if a tumour is present or not. Hence, this is a multiclass classification problem.

## Repository structure

This repositiory is made of 3 main files/scripts used for Tasks A and B respectively. The detailed breakdown of these main files and an average runtime for each is given below. *Note: The runtimes are based on running the script using Google Colab on the High-RAM and GPU hardware accelerator settings.*

* `Task A using Logistic Regression.ipynb` is used to run the binary classifier for Task A using the Logistic Regression model. This trains a Logistic Regression model using the dataset uploaded and then tests it using both the dataset uploaded and the new testing set uploaded a week before the deadline. The testing outputs classification reports and confusion matrices. Hyperparameter tuning is also conducted to improve accuracy scores.
    - **The runtime for this script is: 22 mins 8 secs.**
* `Task A using SVM.ipynb`is used to run the binary classifier for Task A using the Support Vector Machine (SVM) model. This trains 3 SVMs (3 different kernel types) using the dataset uploaded and then tests it using both the dataset uploaded and the new testing set uploaded a week before the deadline. The testing outputs classification reports and confusion matrices. Hyperparameter tuning is also conducted to improve accuracy scores and find a final SVM model to use with optimised parameters.
    - **The runtime for this script is: 26 mins 13 secs.**
* `Task B using SVM.ipynb` is used to run the multiclass classifier for Task B using the Support Vector Machine (SVM) model. This trains 6 SVMs (3 different kernel types two times each (once using a one-vs-rest approach and once using a one-vs-one approach)). The models are trained using the dataset uploaded and then tested using both the dataset uploaded and the new testing set uploaded a week before the deadline. The testing outputs classification reports and confusion matrices. Hyperparameter tuning is also conducted to improve accuracy scores and find a final SVM model to use with optimised parameters.
    - **The runtime for this script is: 36 mins 46 secs.**

A breakdown of the other folders and files in the repository is also given below:

* `READme.md` is this file and is used to give general information about the assignment and submission package including file structure, packages required and instructions on how to run.
* `dataset` is the folder containing the original dataset used for both training and testing. It contains 3000 512x12 MRI images of brain scans and a `.csv` file organising these images into 4 classes of tumours: no tumour, pituitary tumour, glioma tumour and meningioma tumour. 
* `test` is the folder uploaded a week before the deadline containing data solely for testing and validation. It is a separated test set with 200 512x512 MRI images of brain cans and a `.csv` file organising them into the same four classes as before. This is separated from the other data and is used to examine for overfitting.
* `.ipynb_checkpoints` contains checkpoints for our files when they are saved on Jupyter Notebook.


## Packages required

For the 3 scripts , many require the same packages and in this section, we highlight each of the packages, which scripts they are needed in and what they are needed to perform. In summary the packages required are `pandas`, `numpy`, `sklearn`, `skimage`, `matplotlib` and `seaborn`.

* `pandas` is required by all 3 scripts. This is mainly used to load and save csv files containing the labels as a dataframe.
* `numpy` is required by all 3 scripts. This is used to manage any arrays and matrices and the calculations performed on them e.g. concatenation. It is also used to convert our images into numpy arrays so they can be processed. It is also used to find means and standard deviations for the learning curves.
* `sklearn` is required by all 3 scripts to manage the models and many of the preprocessing:
- This is also known as the sci-kit learn package and is used to run machine learning algorithms which are built in to the package. 
- It is needed by `Task A using Logistic Regression.ipynb` to call the `LogisticRegression()` model. 
- It is also needed by `Task A using SVM.ipynb` and `Task B using SVM.ipynb` to call `SVC()` for implementation of a support vector machine.
- It also needed in all 3 scripts to handle other ML operation such as confusion matrices, classification reports, accuracy scores, grid searches and so on.
- The preprocessing and decomposition libraries of the package also handle the `StandardScaler()` and `PCA()` functions respectively.
* `skimage` is required by all 3 scripts and is used for image preprocessing. This is also knwon as the sci-kit image package.
- It is used to read the images from the datasets using `imread()` imported `skimage.io`.
- It is used for data preparation such as `rgb2gray()` to convert the images to grayscale.
- It is used in implementing the histogram of oriented gradients using `hog()`.
* `matplotlib` is required by all 3 scripts. It is used to plot the figures seen such as those displaying the HOG images, the explained variance for PCA, the confusion matrices and the ROC curves.
* `seaborn` is required by all 3 scripts. It is also a data visualisation package and is used to called `heatmap()` for the confusion matrix plots.
* `os` is required for `listdir()` but does not have to be installed in the virtual environment as it is part of Python's standard utility modules.
* `datetime` is required for `datetime.now()` to time the different functions and scripts, but it does not have to be installed in the virtual environment as it is part of Python's standard utility modules.

## How to run the code 

These instructions are given under the assumption that the user will be running it using Jupyter Notebook. The steps to run the code for each script is given below:

1. Create a virtual environment and ensure all the packages needed listed above are installed. I personally used Anaconda to manage the packages for my virtual environment.
2. Ensure the `dataset` and `test` folders are in the same folder as the `.ipynb` files as this is how the paths are defined in the files to load the images and labels. This is the default on my repository but this step is given as an extra reminder.
3. Launch Jupyter Notebook^.
4. Open the desired `.ipynb` file. 
5. Press Run to run the cells individually OR go to "Cell" in the top ribbon and select "Run All". This will run the whole script and generate all the results and plots found in the report^^.

^There are lines of code allowing the code to be run using Google Colaboratory. If this is needed, please read the section below.
^^This generates all the results found in the report except for the ROC curves in `Task A using SVM.ipynb` as this requires `probability = True` in the `SVC()`. However, it is usually left as `False` as it reduces running time significantly without affecting accuracy at all. If an ROC curve is required, please read the section below.

## Other special notes and instructions

### Running on Google Colab

The default expectation is that Jupyter Notebook is used and the code has been written and uploaded to that effect. However, as the algorithms run posed a computational burden on my device, I had to use Google Colaboratory to make use of the GPUs and higher RAM settings available which is why there are some lines of code commented out. To run the code on Colab, the following steps must be taken in all scripts to change relevant directory names:

1. Ensure the Google Drive has the .ipynb files and the `dataset` and `test` folders all uploaded to the same folder.
2. In cell 1, uncomment the code as this allows the Google Drive to be mounted so that the datasets can be imported/loaded. 
3. In cell 4 (the first cell under Loading the data from the data sets), comment out the line 10 and unomment line 9 so that the path being called is `label_path_GDrive`.
4. In cell 8 (the first cell under Data Preparation: Loading the Images), change the word `directory` in lines 32 and 33 to `drive_directory` so that the Google Drive path is used instead of the regular one.
5. In the first cell under the subheadings **Loading the labels and images from the test set**, comment out line 4 and uncomment line 3 to ensure the path being called is that of the Google Drive rather than the regular path used.
6. In the first cell under the subheading **Test set images loading**, change the word `directoryNEW` in lines 32 and 33 to `drive_directoryNEW` so that the Google Drive path is used instead of the regular one.
7. Reverse all these changes if you need to shift back to using Jupyter Notebook. To do this, go through steps 1 - 6 and comment out any lines that were commented and uncomment any lines that were commented. Furthermore, change back the directory names from Steps 4 and 6 to `directory` and `directoryNEW` respectively.
. 
### Generating ROC Curves for Task A using SVM

To generate ROC curves for `Task A using SVM.ipynb`, first run the script as described above. After that is finished, go back to the cell for Model 1 and set probaility to True such that line X reads ` `. Rerun this cell only using `Ctrl + Enter` and then run the two cells for the ROC curves only. Then go back and reset the probability of Model 1 to False.

### Leaving the images in RGB instead of converting to Grayscale (NOT RECOMMENDED)

If the user wishes to leave the images in RGB format rather than convert to Grayscale, refer to the instructions in Cell 8 about commenting out lines 34-36 and uncommenting lines 38-39 in Cell 8. However, this is not recommended as it increases runtime significantly and does not improve accuracy.