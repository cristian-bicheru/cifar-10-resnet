# Training a custom ResNet on the CIFAR-10 dataset

This Jupyter Notebook shows how to train a ResNet on CIFAR-10 in TensorFlow, and uses tactics like L2 normalization, Spatial Dropout, and Data Augmentation to improve model performance.

This model achieves an accuracy of 94.15% on the validation dataset, which rivals [that of humans](http://karpathy.github.io/2011/04/27/manually-classifying-cifar10/).

Training was done on a single mezzanine V100 provided by Google Colab (requires Pro subscription). It took approximately 9 hours to train fully, though I suspect training can be done significantly faster by using ADAM first, and switching to SGD after the ADAM optimizer stops converging.

The model could also be made faster by switching some of the skip connections to use Add() layers instead of Concatenate(). There doesn't seem to be a significant penalty for doing so. Though reszing of the layers using 1x1 convolutions as was done in the original ResNet paper may slightly degrade some of the benefits skip connections offer.

Pre-trained weights are available at [this link](https://drive.google.com/file/d/1nPu9BFSQqsc3Oml0YOsKd8IxQLKVM3HZ/view?usp=sharing).

The confusion matrix produces results which are to be expected. The animals can be particularily challenging to discern, in particular dogs vs cats. This is reflected in the matrix. Similarily automobiles and trucks have some interference.

### Contact Info

Cristian Bicheru - c.bicheru0@gmail.com