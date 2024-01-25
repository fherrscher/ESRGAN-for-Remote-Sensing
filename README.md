# ESRGAN for Remote Sensing Data

This repository was created as part of my master's thesis "Using Super-Resolution GAN for enhanced mapping of urban im-pervious surfaces in Sentinel-2 imagery in Bochum, Germany".

This repo uses the pytorch-implementation of an ESRGAN by [Aladdin Persson](https://github.com/aladdinpersson/Machine-Learning-Collection) as a basis.

> Read the original papers of SRGAN (Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network - Ledig et al. 2017) and of ESRGAN (ESRGAN: Enhanced Super-Resolution Generative Adversarial Networks - Wang et al. 2018) for further information.


**Note: This model only works with 4-band GeoTiffs!**


# Tutorial

## Requirements

All libraries contained in the "requirements.txt" are required. 
It is recommended to download Pytorch from the [official website](https://pytorch.org/).
All libraries can be installed using this command:
```
pip install -r requirements.txt
```

## Test the model

A pre-trained model can be used to test the model. To do this, download the weights from [this link](https://ruhr-uni-bochum.sciebo.de/s/s0E4kQAorZyF9Aj) and copy them into the "checkpoints" folder. Then open "test.py" and change the image path to the desired image. The "test.py" can then be executed and the generated image is saved in the same folder as the input image. 

**Note: the pre-trained model only works with 4-band GeoTiffs with the band arrangement Red-Green-Blue-NIR**

## Train the model

Training data is required to train the model itself. These must be 4-band GeoTiffs. It does not matter which bands are used, but they should correspond to what should be upscaled later.
A subfolder "data" must be created and the training images inserted there. Only a high-resolution image version is required, the corresponding low-resolution version is created automatically by the model.
Configurations can be made to the model in "config.py". However, the settings can be left as they are for now. The batch size may have to be changed depending on the CPU/GPU and the LAMDA_GP depending on the training data. However, this must be found out by trial and error.
You can then start the training process by executing "train.py".