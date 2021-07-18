# Image-Colorizer

This project is the implementation of a Conditional Generative adverserial network algorithm as given in this research paper. To do so, I have used this dataset available on Kaggle.

Here, I've implemented a Gan model which has training and testing datasets that comprise of pairs of 256px by 256px images where one of them is the outline, and the other a colorised version of it.

### Preprocessing

For the preprocessing of the training datasets, we have done Normalization along with Data augmentation by flipping or inverting a few of the images present.

### Generation Model

The Generation Model is used to generate a colorised image of any input outline. This has been built using the UNet architecture, whereby various layers of ConvNets for downsampling are followed by layers of ConvTransposes along with skipping layers which would generate a final matrix the same size as the original image.

### Discriminator Model

The Discriminator Model is just a simpler model to check whether or not a given colorised image is a true image or has been generated using the above model. For this, we would use a simple ConvNet model.

### Loss Function and Optimizer

The loss function is the Sigmoid Cross-Entropy loss.

The optimizer used is the adam optimizer.

###Specs Used

CPU: Intel i5 8th Gen
GPU: Kaggle's in-built GPU along with Nvidia GeForce GTX present on my local system

### Results

Here, as you can see, the images produced before the first epoch barely observes the outlines present in the image to be colorized.

However, by the 15th epoch, the images become much more pronouced. although the color is different for them, the texture and color gradient between images remains very similar to the original image. Do note that further epochs do improve the accuracy, but the running time becomes really high for the algorithm.

You would be able to see the final images at the end of the given .ipynb file in this repo.
