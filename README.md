# Gesture-Recognition
Created a model that identifies the gestures using CNN-RNN model

## Problem Statement:
To develop a cool feature in the smart-TV that can recognise five different gestures performed by the user which will help users control the TV without using a remote, need to build a system for gesture recognition.
The gestures are continuously monitored by the webcam mounted on the TV. Each gesture corresponds to a specific command:

1. Thumbs up:  Increase the volume
2. Thumbs down: Decrease the volume
3. Left swipe: 'Jump' backwards 10 seconds
4. Right swipe: 'Jump' forward 10 seconds  
5. Stop: Pause the movie

## Understanding the Dataset:
The training data consists of a few hundred videos categorised into one of the five classes. Each video (typically 2-3 seconds long) is divided into a sequence of 30 frames(images). These videos have been recorded by various people performing one of the five gestures in front of a webcam - similar to what the smart TV will use.
All images in a particular video subfolder have the same dimensions but different videos may have different dimensions. Specifically, videos have two types of dimensions - either 360x360 or 120x160 (depending on the webcam used to record the videos). 

## Architecture used:
Here we used the standard CNN + RNN architecture in which the conv2D network extracts a feature vector for each image, and a sequence of these feature vectors is then fed to an RNN-based network. The output layer of the RNN is a regular softmax (for a classification problem such as this one).
Fed data to the model in batches using generators. 
Experimented with batch sizes, no of frames, image size, no of layers, dropout values, optimizers and no of epochs
We tried with both LSTM and GRU and observed that GRU is giving better result.
Developed a model that is able to train without any errors and attained an accuracy of 84%.
