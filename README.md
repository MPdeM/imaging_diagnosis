# imaging_diagnosis
This project aims to use X-Ray lung images to detect COVI-19 positive cases using Machine learning. 
Using deep learning techniques for image analysis and classification Xray images can be used to spot anomalies and aid health personel in the diagnosis. 
Disclosure: the work in here is purelly exploratory and IT IS NOT INTENDED FOR DIAGNOSTIC PURPOSES. 


By CDC/ Alissa Eckert, MS; Dan Higgins, MAM - This media comes from the Centers for Disease Control and Prevention's Public Health Image Library (PHIL), with identification number #23312.Note: Not all PHIL images are public domain; be sure to check copyright status and credit authors and content providers., Public Domain, https://commons.wikimedia.org/w/index.php?curid=86444014



Requirements
The main requirements are listed below:

Tested with Tensorflow 
OpenCV 4.2.0
Python 3.6
Numpy
Scikit-Learn
Matplotlib

Additional requirements to generate dataset:

PyDicom
Pandas
Jupyter/CoLab

Data
In machine learning good quality data is key. The datasets are contructed from:

-https://github.com/ieee8023/covid-chestxray-dataset
-https://www.kaggle.com/c/rsna-pneumonia-detection-challenge (which came from: https://nihcc.app.box.com/v/ChestXray-NIHCC)

 The date set were fetched by cloning the github repository and dowloading the rsna pneumonia dataset. 
 For this purpose the datasets were dowloaded to Google Drive. Those two those datasets were then combined into a directory with covid x-rays and non-covid x-rays. 

PROCESSING

 1 Build a normal and covid-19 xray datasets 
 2 Preprocess data by changing color and reshaping to (224,224) , default input size for the model
 3 Normalizing for deep learning and perform one-hot 
 4 Build the train and the test sets 


MODELING 

Create a Convolutional Neural Network using Keras, TensorFlow and deep learning  in Google Colab. 

1 load the VGG16 network https://keras.io/applications/#vgg16
2 model is compiled using Adam optimizer and fit using 10 epocs
 
EVALUATION AND PREDICTION

1 Model was tested with unseen data with a precission of 96% 
2 The model was saved using HDF5 binary format

The model has an accuracy of 96% based only on x-ray images and no other feature. Sensitivity of 96 % and specificity of 95% means that from patients that HAVE COVID-19 the model accurately identify them as positive in 96% of the cases. From patients that do NOT HAVE COVID-19, the model identified as covid negative 96 % of the time. 
As always how good or bad is any diagnosis tool depends on the context that is used. In this case it will be really bad if the model missed a covid-19 positive and goes home thinking is negative and spreads the infection further. 
loss: 0.2678 - accuracy: 0.9565

IMPORT AND CHECK YOUR OWN XRAY IMAGES

The last part is meand to check how good is with new data. 
1 I dowloaded some images on my Google Drive 
2 load, image preprocess (color conversion, re-sizing, scaling)
3 re-shaping array 
4 prediction  
In our case it was able to predict positive to a image that actually was positive!!!






Credits
This notebook is based on-  https://www.pyimagesearch.com/2020/03/16/detecting-covid-19-in-x-ray-images-with-keras-tensorflow-and-deep-learning/
and this paper  https://arxiv.org/pdf/2003.09871v3.pdf



* Marina Marinkovic: [LinkedIn](https://www.linkedin.com/in/marinamarinkovic/) | [GitHub](https://github.com/MPdeM)