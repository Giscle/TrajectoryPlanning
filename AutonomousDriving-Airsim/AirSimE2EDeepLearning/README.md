# Autonomous Driving using End-to-End Deep Learning - AirSim

## Overview

In this tutorial, you will learn how to train and test an end-to-end deep learning model for autonomous driving using data collected from the [AirSim simulation environment](https://github.com/Microsoft/AirSim). You will train a model to learn how to steer a car through a portion of the Mountain/Landscape map in AirSim using a single front facing webcam for visual input. Such a task is usually considered the "hello world" of autonomous driving, but after finishing this tutorial you will have enough background to start exploring new ideas on your own. Through the length of this tutorial, you will also learn some practical aspects and nuances of working with end-to-end deep learning methods.

Here's a short sample of the model in action:

![car-driving](car_driving.gif)



## Structure of this tutorial

The code presented in this tutorial is written in [Keras](https://keras.io/), a high-level deep learning Python API capable of running on top of [CNTK](https://www.microsoft.com/en-us/cognitive-toolkit/), [TensorFlow](https://www.tensorflow.org/) or [Theano](http://deeplearning.net/software/theano/index.html). The fact that Keras lets you work with the deep learning framework of your choice, along with its simplicity of use, makes it an ideal choice for beginners, eliminating the learning curve that comes with most popular frameworks.

This tutorial is presented to you in the form of Python notebooks. Python notebooks make it easy for you to read instructions and explanations, and write and run code in the same file, all with the comfort of working in your browser window. You will go through the following order:

**[DataExplorationAndPreparation](Data.py)**

**[TrainModel](Train.py)**

**[TestModel](Test.py)**


### Environment Setup

1. [Install Anaconda](https://conda.io/docs/user-guide/install/index.html) with Python 3.5 or higher.
2. [Install CNTK](https://docs.microsoft.com/en-us/cognitive-toolkit/Setup-CNTK-on-your-machine) or [install Tensorflow](https://www.tensorflow.org/install/install_windows)
3. [Install h5py](http://docs.h5py.org/en/latest/build.html)
4. [Install Keras](https://keras.io/#installation) and [configure the Keras backend](https://keras.io/backend/) to work with TensorFlow (default) or CNTK.
5. [Install AzCopy](https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy). Be sure to add the location for the AzCopy executable to your system path.
6. Install the other dependencies. From your anaconda environment, run "InstallPackages.py" as root or administrator. This installs the following packages into your environment:
    * jupyter
    * matplotlib v. 2.1.2
    * image
    * keras_tqdm
    * opencv
    * msgpack-rpc-python
    * pandas
    * numpy
    * scipy

### Simulator Package

We have created a standalone build of the AirSim simulation environment for the tutorials in this cookbook. [You can download the build package from here](https://airsimtutorialdataset.blob.core.windows.net/e2edl/AD_Cookbook_AirSim.7z). 
### Dataset

The dataset for the model is quite large. [You can download it from here](https://aka.ms/AirSimTutorialDataset).
