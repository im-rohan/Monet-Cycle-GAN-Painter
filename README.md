# Monet-Cycle-GAN-Painter

This project is a submission for a Kaggle competition - <a href="https://www.kaggle.com/competitions/gan-getting-started">I’m Something of a Painter Myself</a><br>
and as the final project for CS 6140 class

## Dataset and Descriptions

**Dataset Used: <a href="https://www.kaggle.com/competitions/gan-getting-started/data">Kaggle Monet GAN Dataset</a>**

The dataset contains four directories: monet_tfrec, photo_tfrec, monet_jpg, and photo_jpg. The monet_tfrec and monet_jpg directories contain the same painting images, and the photo_tfrec and photo_jpg directories contain the same photos.

monet_jpg - 300 Monet paintings sized 256x256 in JPEG format<br>
monet_tfrec - 300 Monet paintings sized 256x256 in TFRecord format<br>
photo_jpg - 7028 photos sized 256x256 in JPEG format<br>
photo_tfrec - 7028 photos sized 256x256 in TFRecord format

Images are JPEG format, 256x256 resolution, RGB color channels.<br>
Preprocessing includes resizing to 286x286, random cropping to 256x256, random horizontal flipping, and normalization to [-1, 1].

### Model Selection

We used the Deep Learning GAN model - CycleGAN

**Generator**:<br>
Encoder-decoder U-Net style.<br>
Skip connections between encoder and decoder.<br>
Uses Conv2D, Conv2DTranspose, GroupNorm, LeakyReLU, Tanh activation.

**Discriminator**:<br>
PatchGAN classifier.<br>
Outputs 70x70 patch-based discrimination.<br>
Conv layers with GroupNorm and LeakyReLU.

CycleGAN is used as it works with unpaired datasets and it enables bidirectional domain learning.

**Model Summary**:

2 Generators<br>
2 Discriminators (PatchGAN)<br>
