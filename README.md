Get the data sources from https://btsd.ethz.ch/shareddata/ 
(Belgian Traffic Sign Detection data set)

Unzip archives into separate directories

- https://btsd.ethz.ch/shareddata/BelgiumTSC/BelgiumTSC_Training.zip > /hdd/data/Training
- https://btsd.ethz.ch/shareddata/BelgiumTSC/BelgiumTSC_Testing.zip > /hdd/data/Testing

Make sure that Training and Testing include subfolders 00000 to 00061 corresponding to the classes of the traffic sign. Each folder contains sample images in PPM format.

Data set includes 62 classes of traffic signs. Each image is in PPM format can be loaded by skimage package in Python. Make sure to transform images to uniformly sized inputs.

SimpleTSR.py loads test and training data, converts to 32x32 images in RGB space, builds a simple neural network with NO HIDDEN LAYERS and trains for 401 epochs using a learning rate of 0.001 using ReLU activation function. Classification is based on maximum logit in the output laye to assign an image to one of the 62 traffic sign classes.

Code uses packages skimage, tensorflow and numpy. 

Tested on Windows and Linux using TensorFlow 1.8. 

WARNING:
THis is a quick two hour hack, intended to be improved by my students, e.g. by adding more layers, more fancy image processing, using convolutional neural networks, and proper logging using TensorBoard visualization of learning progress.

ONLY ACHIEVES ABOUT 70% accuracy.