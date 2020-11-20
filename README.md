# Convolutional neural newtork for image classification

Developed by: A. Santopaolo (2019).

Supervisor: prof. L. Iocchi.

Achievement: Machine Learning exam (partial).


Convolutional Neural Networks are used since they are able to deal with multi-dimensional data by means of a kernel that moves along the image and perform some operations on it, so as to obtain some new representation of that image.

Two different approaches are followed in this work: first, a Convolutional Neural Network is created, trained and tested. It is named MugnanoNet. Then, transfer learning is applied: in this way, a pre-trained model is used and compared with MugnanoNet.

<h3> Dataset </h3>
A weather dataset is used. It is stored in Google Drive, and it is divided into different folders. Four classes are considered: haze, sunny, snowy, rainy. The dataset is balanced, therefore the accuracy is chosen as main metric for the evaluation. Also a blind test set is used at the end of the project.

<h3>MugnanoNet</h3>
Structure of the network:
- Input layer is of size 227x227x3
-  Convolutional layer with kernel size of 11x11x3, 96 such kernels
-  Max pooling layer with size 3x3 and stride 2
-  Convolutional layer with kernel size of 5x5x96, 256 such kernels
-  Max pooling layer with size 3x3 and stride 2
- Convolutional layer with kernel size of 3x3x256, 384 such kernels, padding to maintain width and height
-  Convolutional layer with kernel size of 3x3x384, 384 such kernels, padding to maintain width and height
-  Convolutional layer with kernel size of 3x3x384, 256 such kernels, padding to maintain width and height
-  Max pooling layer with size 3x3 and stride 3
- Fully connected layer with 4096 neurons
-  Fully connected layer with 4096 neurons
-  Fully connected layer with 64 neurons
-  Softmax classification layer with 4 classes

Heavy fluctuation of the results are obtained, probably due to under-fitting. The accuracy obtained is 0.65.

<h3>Transfer Learning</h3>
  
Downloaded VGG16 with parameters trained with Imagenet.  Set the 3rd convoloutional layer of the 5th block trainable. Flattened the layers. Added two dense layers with  100 and 64 neurons respectively,added dropout after dense layers and also used L2 regularisaton for thes etrainable  dense  layers.   Finally  passed  to  the  output  layer  with  softmaxactivation to get the final prediction of the classes. Got good performace.

<h3>Implementation Details</h3>
The code has been written in Google Colaboratory for Python. The dataset is stored in a personal Google Drive folder. The code is available, and can be opened in Colab. To run, you need to link a valid dataset via Drive or other storing platforms.
