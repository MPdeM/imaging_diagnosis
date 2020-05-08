#### imaging_diagnosis: NOT FOR CLINICAL USE

### COVID-19 X-Rays PREDICTOR
Project Summary: to use X-Ray lung images to detect COVI-19 positive cases using Machine Learning. 

Deep learning techniques for image analysis and classification Xray images can be used to spot anomalies and aid health personel in the diagnosis. 

##  the work in here is purelly exploratory and IT IS NOT INTENDED FOR DIAGNOSTIC PURPOSES. 

![](images/SARS-CoV-2_without_background.png)

By CDC/ Alissa Eckert, MS; Dan Higgins, MAM - from CDC (https://commons.wikimedia.org/w/index.php?curid=86444014)



## Requirements
The main requirements are listed below:

- Tested with Tensorflow 
- OpenCV 4.2.0
- Python 3.6
- Numpy
- Scikit-Learn
- Matplotlib

Additional requirements to generate dataset:

- PyDicom
- Pandas
- Jupyter/CoLab

## Data
In ML good quality data is key. The datasets are contructed from:

- https://github.com/ieee8023/covid-chestxray-dataset
- https://www.kaggle.com/c/rsna-pneumonia-detection-challenge (which came from: https://nihcc.app.box.com/v/ChestXray-NIHCC)

The obtain the dateset with covid-19 images I cloned the repository and dowloaded the metadata.csv and /images/ folder into a folder /covid-chest-xray/ in my goggle drive '/content/drive/My Drive/covid-chest-xray/'
To obtain the dataset for the normal x-rays I dowloaded the rsna pneumonia dataset and dowloaded the data into a folder '/pneumonia-chest-xray/' in my goggle drive. 

Those two those datasets were then combined into a directory with covid x-rays ['/data/covid'](data/covid) and non-covid x-rays ['/data/normal'](data/normal)  

## Inspect the Metadata of the Covid-19 dataset
The [metadata](metadata.csv) from the Covid dataset has interesting information about the images like findings (COVID, SARS, MERS, PNEuMONIA among others) sex, age, survival, or views. The set I am intereste is the Posteroanterior view (PA) and findinds : Covid-19. 

## PROCESSING

 - 1 Build a normal ['/data/normal'](data/normal) and covid-19 xray['/data/covid'](data/covid) datasets
 - 2 Preprocess data by changing color and reshaping to (224,224) , default input size for the model
 - 3 Normalizing for deep learning and perform one-hot 
 - 4 Build the train and the test sets 


## MODELING 

Create a Convolutional Neural Network using Keras, TensorFlow and deep learning in Google Colab. 

- 1 load the VGG16 network https://keras.io/applications/#vgg16
- 2 model is compiled using Adam optimizer and fit using 10 epocs

 ![](images/Training.PNG)

## EVALUATION AND PREDICTION

- 1 Model was tested with unseen data with a precission of 96% 
- 2 The model was saved using HDF5 binary format

![](images/ClassReport.PNG)

The model has an accuracy of 96% based only on x-ray images and no other feature. Sensitivity of 96 % and specificity of 95% means that from patients that HAVE COVID-19 the model accurately identify them as positive in 96% of the cases. From patients that do NOT HAVE COVID-19, the model identified as covid negative 96 % of the time. 

![](images/SensSpec.PNG)

As always how good or bad is any diagnosis tool depends on the context that is used. In this case it will be really bad if the model missed a covid-19 positive and goes home thinking is negative and spreads the infection further. 

[loss: 0.2678 - accuracy: 0.9565]

##  CHECK YOUR OWN XRAY IMAGES

The last part is meant to allow to check x-ray images for covid-19. This is what I did: 
 
- 1 I dowloaded some images on my Google Drive. In this exaple I donwloaded an image Case courtesy of Dr Fabio Macori, Radiopaedia.org. From the case rID: 74887  
![](images/covid-19-pneumonia-14.png)

- 2 load the image to CoLab, and performed image preprocess (color conversion, re-sizing, and scaling)
- 3 re-shaping array 
- 4 load the model and do prediction  

In our case it was able to predict positive to a image that actually was positive!!!




Credits
This notebook is based on the tutorial [here](https://www.pyimagesearch.com/2020/03/16/detecting-covid-19-in-x-ray-images-with-keras-tensorflow-and-deep-learning/)
and this paper [here](https://arxiv.org/pdf/2003.09871v3.pdf) and tons of medium articles 


## Contact

* Marina Marinkovic / PdeM: [LinkedIn](https://www.linkedin.com/in/marinamarinkovic/) | [GitHub](https://github.com/MPdeM)