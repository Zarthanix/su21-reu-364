---
date: 2021-06-16
title: "Project: Hand Tracking with AI"
linkTitle: "Hand Tracking"
tags: ["project", "reu", "ai", "communication"]
description: "In this project we study the ability of an AI to recognize letters from the American Sign Language (ASL) alphabet. We use a Convolutional Neural Network and apply it to a dataset of hands in different positionings showing the letters 'a', 'b', and 'c' in ASL. With this we build a model to recognize the letter and output the letter it predicts."
author: David, Umanzor
github_url: https://github.com/cybertraining-dsc/su21-reu-364/edit/main/project/index.md
resources:
- src: "**.{png,jpg}"
  title: "Image #:counter"
---

[![Check Report](https://github.com/cybertraining-dsc/su21-reu-364/workflows/Check%20Report/badge.svg)](https://github.com/cybertraining-dsc/su21-reu-364/actions)
[![Status](https://github.com/cybertraining-dsc/su21-reu-364/workflows/Status/badge.svg)](https://github.com/cybertraining-dsc/su21-reu-364/actions)
Status: draft, Type: Project


David Umanzor, [su21-reu-364](https://github.com/cybertraining-dsc/su21-reu-364), [Edit](https://github.com/cybertraining-dsc/su21-reu-364/blob/main/project/index.md)

{{% pageinfo %}}

## Abstract

In this project, we study the ability of an AI to recognize letters from the American Sign Language (ASL) alphabet. We use a Convolutional Neural Network and apply it to a dataset of hands in different positionings showing the letters 'a', 'b', and 'c' in ASL. The proposed CNN model receives an ASL image and recognizes the feature of the image, generating the predicted letter.

Contents

{{< table_of_contents >}}

{{% /pageinfo %}}

**Keywords:** ai, object recognition, image processing, computer vision, american sign language. 

## 1. Introduction

Object detection and feature selection are essential tasks in computer vision and have been approached from various perspectives over the past few decades [^1]. The brain uses object recognition to solve an inverse problem: one where (surface properties, shapes, and arrangements of objects) need to be inferred from the perceived outcome of the image formation process [^3]. Visual object recognition as a neural substrate in humans was revealed by neuropsychological studies. There are specific brain regions that cause object recognition, yet we still do not understand how the brain achieves this remarkable behavior [^2]. Human beings rely and rapidly recognize objects despite considerable retinal image transformations arising from changes in lighting, image size, position, and viewing angle [^2].

A gesture is a form of nonverbal communication done with positions and movements of the hand, arms, body parts, hand shapes, movements of the lips or face [^4]. One of the key differences of hand gestures is that they allow communication over a long distance [^5]. American Sign Language (ASL) is a formal language that has the same lingual properties as oral languages commonly used by deaf people to communicate [6]. ASL typically is formed by the finger, hand, and arm positioning and can contain static and dynamic movement or a combination of both to communicate words and meanings to another [^7]. Communication with other people can be challenging because people are not typically willing to learn sign language [^7].

In this paper, we consider the problem of detecting and understanding American Sign Language. We test CNN's ability to recognize the ASL alphabet. As advancements in technology increase, there are more improvements to 2D methods of hand detection. Commonly these methods are visual-based, using color, shape, and edge to detect and recognize the hand [^8]. There are issues to these technologies like inconsistent lighting conditions, non-hand color similarity, and varying viewpoints that can decrease the model's ability to recognize the hand and its positioning. We use a Convolutional Neural Network to create the model and detect different letters of American Sign Language.

## 2. Data Sets

In this research we use two sources of datasets, the first is from kaggle which it was already prepared but we needed more. The second is self made dataset by take images in good lighting against a white wall, it was then cropped to 400x400 pixels focused on the hand. The program then sets the images to grayscale as the color is not needed for this research. Finally, the images are reduced to 50x50 resolution for the AI to use for training.

![Figure 1](https://github.com/cybertraining-dsc/su21-reu-364/raw/main/project/images/Hand%20B%20Dataset%20Demo.png)

**Figure 1:** Dataset of hands doing different alphabet letters in ASL [^5].

## 3. Documentation

![Figure 2](https://github.com/cybertraining-dsc/su21-reu-364/raw/main/project/images/CNNDiagram.png)

**Figure 2:** The Convolutional Neural Network (CNN) model.

This model shows the CNN model that we used to train the AI. The CNN takes pictures and breaks them down into smaller segments called features. It is trained to find patterns and features over the images allowing the CNN to predict an 'a', 'b', or 'c' upon the given ASL image with high accuracy. A CNN uses a convolution operation that filters every possible position the feature it collected can be matched to and attempts to find where it fits in [^10]. This process is repeated and becomes the convolution layer or in the image depicted as Conv2d + Relu. The ReLU stands for the rectified linear unit and is used as an activation function for the CNN [^11].

## 4. Methodology

In this research we use three sources of data-sets, the first two is from kaggle which it was already prepared but we needed more. The second is self-made data-set by take images in good lighting against a white wall, it was then cropped to 400ppi (pixels per inch) focused on the hand. The program then sets the images to gray-scale as the color is not needed for this research. Finally, the images are reduced to different resolutions for the AI to use for training

We built the model using a convolution neural network (CNN) to create an AI that can recognize ASL letters (’a’, ’b’, and ’c’), using a collection of 2,526 images. The Data-set contains 842 images for each letter to train the AI’s CNN. This can be expanded to allow an AI to recognize letters, words, and any expression that can be made using a still image of the hands. A CNN fits this perfectly as we can use its ability to assign importance to segments of an image and tell the difference from one another using weights and biases. With the proper training, it is able to learn and identify these characteristics.

Keras Conv2D is a 2D Convolution Layer, this layer creates a convolution kernel that is wind with layers input which helps produce a tensor of outputs.

ReLu, Rectified Linear Unit activation function that outputs the input directly if it is positive, otherwise it outputs zero. We employed the Leaky ReLu which allows for a small positive gradient when the unit is not active.

Maxpooling, uses a 2 x 2 sized kernel to not lose important features of the input with strides equals to 2. Every time 2 x 2 sized kernel shifts 2 times, it reduces the size of an image by half.

Flattening converts the data into a 1-dimensional array for inputting towards the next layer. It creates a singular feature vector and then is connected to the classification model.

Fully Connected layer is feed forward neural networks in which the input is from the flattened 1-dimensional array and performs a linear transformation and a non-linear transformation.

Linear Transformation equation

Z = WT.X + b

Non-Linear Transformation equation

f(x) = 1/(1+e^-x)

Softmax is the final layer in the neural network and will perform the operations for the model to calculate multi-class classification like in the case of the research it is used to output the label of if the model recognizes the image as an "a", "b", or "c" class.


## 5. Benchmark

![Figure 3](https://github.com/cybertraining-dsc/su21-reu-364/raw/main/project/images/ConfusionMatrixCNN.png)

**Figure 3:** The Confusion Matrix of the finished CNN model.

The Confusion Matrix shows the results of the model after being tested on its ability to recognize each letter, in the image it shows that the AI had a difficult time recognizing the difference between an 'a' and 'c' only getting 6% of the images labelled as 'c' correct.

## 6. Conclusion

We build a model to recognize an ASL given an image and identify the corresponding letter using a convolutional neural network. The model showed the best results at 75ppi running 5 epochs for an accuracy of 99% in both "a" and "b" classes then a 95% in class "c". Comparing the results shows that 2 epochs had a trend to being underfit for our data set while the 10 epochs would be overfitting for our data. Having an image size of 75ppi would leave to the program being able to learn from more important parts of the data rather than background noise and smaller unnecessary details for it to make an accurate prediction. This is seen in how moving to a higher resolution had a decreasing return on the average accuracy for the models.

Future studies using a larger data-set can be applied to more complex methods than just singular letters but words from the ASL language to recreate a text to speech software based around ASL hand positioning.

## 7. Acknowledgments

We thank Carlos Theran (Florida A & M University) for advising, guidance, and resources used in the research; We thank Yohn Jairo (Florida A & M University) for guidance and aid on the research report; We thank Gregor von Laszewki (Florida A & M University) for advice and commenting on the code and report; We thank the Polk State LSAMP Program for aid in obtaining this opportunity. We thank Florida A & M University for funding this research.

## 8. References

[^1]: Pan, T.-Y., Zhang, C., Li, Y., Hu, H., Xuan, D., Changpinyo, S., Gong, B., &amp; Chao, W.-L. (2021, July 5). On Model Calibration for Long-Tailed Object Detection and Instance Segmentation. arXiv.org.
      https://arxiv.org/abs/2107.02170. 

[^2]: Wardle, S. G., & Baker, C. (2020). Recent advances in understanding object recognition in the human brain: Deep neural networks, temporal dynamics, and context. F1000Research. F1000 Research Ltd.
      <https://doi.org/10.12688/f1000research.22296.1>

[^3]: Wardle, S. G., & Baker, C. (2020). Recent advances in understanding object recognition in the human brain: Deep neural networks, temporal dynamics, and context. F1000Research. F1000 Research Ltd. 
      <https://doi.org/10.12688/f1000research.22296.1>

[^4]: Dabre, K., & Dholay, S. (2014). Machine learning model for sign language interpretation using webcam images. 2014 International Conference on Circuits, Systems, Communication and Information Technology Applications (CSCITA), 317-321.
      <https://ieeexplore.ieee.org/document/6839279>

[^5]: tecperson, Sign Language MNIST Drop-In Replacement for MNIST for Hand Gesture Recognition Tasks, [Kaggle] 
      <https://www.kaggle.com/datamunge/sign-language-mnist>

[^6]: U.S. Department of Health and Human Services. (n.d.). American Sign Language. National Institute of Deafness and Other Communication Disorders.
      <https://www.nidcd.nih.gov/health/american-sign-language>

[^7]: A. Rahagiyanto, A. Basuki, R. Sigit, A. Anwar and M. Zikky, "Hand Gesture Classification for Sign Language Using Artificial Neural Network," 2017 21st International Computer Science and Engineering Conference (ICSEC), 2017, pp. 1-5, 
      <doi: 10.1109/ICSEC.2017.8443898>

[^8]: Jiayi Wang, Franziska Mueller, Florian Bernard, Suzanne Sorli, Oleksandr Sotnychenko, Neng Qian, Miguel A. Otaduy, Dan Casas, and Christian Theobalt. 2020. RGB2Hands: real-time tracking of 3D hand interactions from monocular RGB video. ACM Trans. Graph. 39, 6, Article 218 (December 2020), 16 pages.
      <https://doi.org/10.1145/3414685.3417852>
 
[^9]: Tatan, V. (2019, December 23). Understanding CNN (convolutional neural network). Towards Data Science. 
      <https://towardsdatascience.com/understanding-cnn-convolutional-neural-network-69fd626ee7d4>

[^10]: Rohrer, B. (2016, August 18). How do Convolutional Neural Networks work? Library for end-to-end machine learning. 
      <https://e2eml.school/how_convolutional_neural_networks_work.html>

[^11]: Patel, K. (2020, October 18). Convolution neural networks - a beginner's Guide. Towards Data Science.
      <https://towardsdatascience.com/convolution-neural-networks-a-beginners-guide-implementing-a-mnist-hand-written-digit-8aa60330d022>
