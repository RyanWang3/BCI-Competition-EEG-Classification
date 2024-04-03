# BCI-Competition-EEG-Classification

A CNN architecture for classifying cued motor imagery from EEG data. 

## Dataset

This data comes from BCI competition IV 'data sets 2a'. This dataset is made publicly available through: http://www.bbci.de/competition/iv/. 

## Architecture

Since ILSVRC2012 where AlexNet dropped the top-5 error by 10.4 percent, CNNs have made a resurgence as the starting model for many deep learning tasks. Following the steps of Tonio Ball et al., we decided to implement our own CNN model that crucially forgoes their discrete temporal and spatial convolution for a simple single convolution layer allowing our model to learn its own mapping without restraint.

Inspired VGGnet, we chose small (3x3) filters for the convolution layers. Corresponding to these smaller filters, we expanded the depth to 100 filters thus leveraging the advantages of a bigger receptive field as well as adding more non-linearity. Furthermore, with insight that more layers have empircally been shown to offer advantages, after trying variable number of convolution blocks, we settled on 4 as it offered the best performance.

## Training

We trained our CNN model for 94 epochs on Google Colab with their CPU which took 18 minutes. This was an adequate amount of time as our validation error started to taper off at this point. Due to the simplistic nature of a standard CNN model, a GPU was not necessary to get our optimal model.

## Performance

Our best model, the CNN, achieved a test accuracy of 71.1%, achieving good performance relative to the  FBCSP algorithm (68% from Tonio Ball et al. implementation). Compared to other algorithms we tested, the CNN performed much better, with the closest model being the CNN+LSTM achieving a test accuracy of 69.1%. 
