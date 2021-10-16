# A Light Deep Neural Network to Detect Fishes in Saudi Arabia in Real-Time.

## Introduction

The core of this project focuses on a keep-growing field in Saudi Arabia, which is the fish market. The Saudi fish market has distinctive species because they only reside in the Gulf Sea or the Red Sea. When it comes to customers, it is difficult to identify the different species if they have no prior knowledge. 

## Problem
New-young customers in Saudi Arabia can find it difficult to distinguish between the fishes. This is because they look similar and have many different species. Since a fish can come in various dimensions, colors, textures, and physical characteristics, there will be different distinctive features that distinguish each species from each other. A CNN model is a suitable approach to this problem. Since each fish species has its unique physical characteristics, we can let the Neural Network recognize the features by itself. 

## Solution
The proposed solution to this problem is to identify and recognize the fish species in real-time, which will help the customers to get a rapid solution of recognizing a fish species. This will be done by implementing a deep neural network model based on ConvNets. Furthermore, the model will be deployed on mobile to facilitate the use of the model for all customers.

## Details of Tools and Design

- Data has been collected from various sources (Social Media, Search Engines, Etc.).
- Data distribution is as follows with each class having at least 100 images and at most 300 images:

Fish Type |
------------ |
Greasy grouper (Hamoor)
Lethrinus Nebulosus (sh3ry or sh3or)
Nemipterus  (3andq)
Pampus Argenteus (Zbeedi)
Kanaad | 65
Siganus rivulatus (Sijan/Safi)


- Data has been processed, such that the fishes have been labeled and boxed for the network to train on, resized/cut for ease of training, as well as the data has been validated by an expert in the field.
- The split size is 90/10 for training and validation.
- TensorFlow Object Detection API (OD API) has been used to train multiple models and then they were tested on unseen data.

## Result
In this repository, you will find only the two models Inception V2 and Mobile Detnet. The training result is shown below is done through TF Sample Application. 

|     Feature Extractor of   SSD Architecture    |     Steps    |     mAP     |     Classification Loss    |     Train Loss    |     Validation Loss    |     Graphs Look    |     Inference Time on   Galaxy S10+       |
|------------------------------------------------|--------------|-------------|----------------------------|-------------------|------------------------|--------------------|-------------------------------------------|
|     Resnet-640                                 |     30K      |     0.8     |     0.19                   |     0.2           |     0.4                |     OK             |     2000ms and did not work.              |
|     Resnet-512                                 |     100K     |     0.72    |     0.24                   |     0.15          |     0.37               |     ish OK         |     3000ms to 3500ms and did not work.    |
|     MobileNet_v1_640                           |     25K      |     0.82    |     0.29                   |     0.38          |     0.64               |     ish OK         |     1500ms to 4000ms                      |
|     Mobile Detnet 300                          |     100K     |     0.77    |     0.17                   |     0.15          |     0.31               |     Great          |     less than 200ms                       |
|     Inception v2 300                           |     200K     |     0.82    |     1.65                   |     1.45          |     2.2                |     Not Stable     |     100 to 300ms                          |
