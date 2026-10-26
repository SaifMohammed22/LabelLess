<div align="center">

# LabelLess

<a href="https://pytorch.org/get-started/locally/"><img alt="PyTorch" src="https://img.shields.io/badge/PyTorch-ee4c2c?logo=pytorch&logoColor=white"></a>
<a href="https://hydra.cc/"><img alt="Config: Hydra" src="https://img.shields.io/badge/Config-Hydra-89b8cd"></a>

</div>

## Problem Definition
We address image classification on CIFAR-10 using a Vision Transformer (ViT) when only a few labeled images are available. Instead of training the ViT only on labeled data, we first pretrain it without labels using a Masked Autoencoder (MAE), where most patches of each image are hidden, and the model learns to reconstruct them. We then fine-tune the pretrained encoder for classification using only 1%, 10%, or 100% of the training labels and compare it with an identical ViT trained from scratch. The central question is how much self-supervised pretraining reduces the number of labels a ViT needs.

## Why is it important?
In many real applications, images are plentiful, but labels and annotations are expensive because they require expert time: radiologists for medical scans, analysts for satellite imagery, or inspectors for industrial defects.

Vision Transformers now dominate computer vision, yet they are **data-hungry** and perform poorly when trained from scratch on small labeled datasets. Showing that self-supervised pretraining lets a ViT reach good accuracy with a small fraction of the labels directly lowers the cost of deploying modern vision models in label-scarce domains.

## Dataset
We're mainly using [CIFAR10](https://cave.cs.toronto.edu/kriz/cifar.html): a dataset consists of 60000 32x32 colour images in 10 classes, with 6000 images per class. There are 50000 training images and 10000 test images.



