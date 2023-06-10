# Attention Incorporated ResNet-18 Backbone for Faster R-CNN (Object Detection)

![image](https://github.com/Ruthvik9/Attttttention-ResNet/assets/74010232/8fa441dc-324c-4530-a291-fe5088cef4f8)

![image](https://github.com/Ruthvik9/Attttttention-ResNet/assets/74010232/b439c059-1fe4-4d6e-ab63-07a39d061970)


This repository contains my implementation of an attention-enhanced ResNet-18 backbone for use with the Faster R-CNN object detection model.




Note: I've used the mmdetection framework to incorporate this backbone into and train my faster-rcnn model. I obtained a very good mAP of 40 given the fact that
the dataset only had 40000 examples belong to 27 different classes and many classes NOT HAVING ENOUGH REPRESENTATIVE EXAMPLES.

## Overview
The aim of this project is to strengthen the standard ResNet-18 backbone by incorporating attention mechanisms, specifically Channel Attention (ECA) and Spatial Attention (Attention Gates), which together result in a more powerful and expressive feature extraction mechanism for object detection tasks.

## Channel and Spatial Attention
Channel Attention, implemented through the ECA module, focuses on the interdependencies between different feature channels. The ECA module adaptively recalibrates channel-wise feature responses by explicitly modelling interdependencies between channels of the convolutional features.

Spatial Attention, on the other hand, is implemented via Attention Gates, which focus on identifying and enhancing the spatially important features while suppressing the less important ones. This mechanism helps the model to focus more on the significant spatial features.

The combination of Channel and Spatial Attention allows the model to selectively emphasise informative features and suppress less useful ones, which can potentially lead to improved performance in object detection.

## Implementation
This implementation extends the ResNet-18 model by incorporating the ECA and Attention Gates at each layer of the backbone. Each feature map is first passed through an ECA module for channel attention, followed by an Attention Gate for spatial attention. The outputs from these layers are used as the backbone feature maps for the Faster R-CNN model.

In addition to attention mechanisms, this implementation also includes optional NonLocal Blocks for capturing long-range dependencies within the feature maps, providing another dimension of feature enhancement.

Why is this a good idea?
Adding attention to the ResNet-18 backbone essentially augments its ability to focus on the important parts of an image while suppressing less important information. This adaptive ability is especially useful for object detection tasks, where the location and scale of objects can vary significantly.

Furthermore, adding attention mechanisms can potentially make the backbone more expressive without introducing a significant computational overhead. This makes it a cost-effective strategy for improving the performance of object detection models.
