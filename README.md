# Fast-Neural-Style-Transfer

Generative Neural Methods Based On Model Iteration

## Description
Using a Deep Residual Convolutional Neural Network as an Image Transformation Network (ITN). We train the ITN to transform input images into output images. We use a VGG19 which is pre-trained on ImageNet dataset as Loss Network to define two Perceptual Losses (Feature Reconstruction Loss & Style Reconstruction Loss) that measure perceptual differences in content and style between images. <br/>For a specific style, we train one ITN using MS-COCO dataset (about 12.6GB). After trained, we can use the ITN to transfer specific style to any image just performing one feed-forward computation.

This code is based on Johnson et al. [Perceptual Losses for Real-Time Style Transfer and Super-Resolution](https://arxiv.org/abs/1603.08155) [2016.03] and Ulyanov et al. [Instance Normalization: The Missing Ingredient for Fast Stylization](https://arxiv.org/abs/1607.08022) [2016.09].

![itn_overview](https://user-images.githubusercontent.com/13844740/33978580-68dc57ea-e0db-11e7-9886-eafba2a436fd.jpg)
System overview. Picture comes from Johnson et al. original paper. In my implementation, I replace the VGG-16 to a pre-trained VGG-19. I use 'relu4_2' layer to compute Feature Reconstruction Loss and use {'relu1_1', 'relu2_1', 'relu3_1', 'relu4_1', 'relu5_1'} layers to compute Style Reconstruction Loss.

## Results
| style | output (generated image) |
| :----: | :----: |
|![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/images/style_thumb/wave_thumb.jpg)|  ![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/outputs/wave-Lance.jpg)  |
|![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/images/style_thumb/udnie_thumb.jpg)|  ![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/outputs/udnie-Lance.jpg)  |
|![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/images/style_thumb/escher_sphere_thumb.jpg)|  ![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/outputs/escher_sphere-Lance.jpg)  |
|![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/images/style_thumb/flower_thumb.jpg)|  ![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/outputs/flower-Lance.jpg)  |
|![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/images/style_thumb/scream_thumb.jpg)|  ![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/outputs/scream-Lance.jpg)  |
|![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/images/style_thumb/denoised_starry_thumb.jpg)|  ![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/outputs/denoised_starry-Lance.jpg)  |
|![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/images/style_thumb/starry_bright_thumb.jpg)|  ![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/outputs/starry_bright-Lance.jpg)  |
|![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/images/style_thumb/rain_princess_thumb.jpg)|  ![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/outputs/rain_princess-Lance.jpg)  |
|![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/images/style_thumb/woman_matisse_thumb.jpg)|  ![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/outputs/woman_matisse-Lance.jpg)  |
|![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/images/style_thumb/mosaic_thumb.jpg)|  ![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/outputs/mosaic-Lance.jpg)  |
|![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/images/style_thumb/wave_thumb.jpg)|  ![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/outputs/wave-stata.jpg)  |
|![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/images/style_thumb/udnie_thumb.jpg)|  ![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/outputs/udnie-stata.jpg)  |
|![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/images/style_thumb/escher_sphere_thumb.jpg)|  ![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/outputs/escher_sphere-stata.jpg)  |
|![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/images/style_thumb/flower_thumb.jpg)|  ![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/outputs/flower-stata.jpg)  |
|![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/images/style_thumb/scream_thumb.jpg)|  ![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/outputs/scream-stata.jpg)  |
|![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/images/style_thumb/denoised_starry_thumb.jpg)|  ![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/outputs/denoised_starry-stata.jpg)  |
|![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/images/style_thumb/starry_bright_thumb.jpg)|  ![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/outputs/starry_bright-stata.jpg)  |
|![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/images/style_thumb/rain_princess_thumb.jpg)|  ![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/outputs/rain_princess-stata.jpg)  |
|![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/images/style_thumb/woman_matisse_thumb.jpg)|  ![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/outputs/woman_matisse-stata.jpg)  |
|![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/images/style_thumb/mosaic_thumb.jpg)|  ![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/outputs/mosaic-stata.jpg)  |
|![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/images/style_thumb/wave_thumb.jpg)|  ![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/outputs/wave-brad_pitt.jpg)  |
|![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/images/style_thumb/udnie_thumb.jpg)|  ![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/outputs/udnie-brad_pitt.jpg)  |
|![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/images/style_thumb/escher_sphere_thumb.jpg)|  ![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/outputs/escher_sphere-brad_pitt.jpg)  |
|![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/images/style_thumb/flower_thumb.jpg)|  ![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/outputs/flower-brad_pitt.jpg)  |
|![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/images/style_thumb/scream_thumb.jpg)|  ![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/outputs/scream-brad_pitt.jpg)  |
|![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/images/style_thumb/denoised_starry_thumb.jpg)|  ![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/outputs/denoised_starry-brad_pitt.jpg)  |
|![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/images/style_thumb/starry_bright_thumb.jpg)|  ![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/outputs/starry_bright-brad_pitt.jpg)  |
|![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/images/style_thumb/rain_princess_thumb.jpg)|  ![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/outputs/rain_princess-brad_pitt.jpg)  |
|![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/images/style_thumb/woman_matisse_thumb.jpg)|  ![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/outputs/woman_matisse-brad_pitt.jpg)  |
|![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/images/style_thumb/mosaic_thumb.jpg)|  ![](https://github.com/elleryqueenhomels/fast_neural_style_transfer/blob/master/outputs/mosaic-brad_pitt.jpg)  |

## Manual
- The main file `main.py` is a demo, which has already contained training procedure and inferring procedure (inferring means generating stylized images).<br />You can switch these two procedures by changing the flag `IS_TRAINING`.
- By default,<br />(1) The content images lie in the folder `"./images/content/"`<br />(2) The style images lie in the folder `"./images/style/"`<br />(3) The weights file of the pre-trained VGG-19 lies in the current working directory. (See `Prerequisites` below)<br />(4) The MS-COCO images dataset for training lies in the folder `"./MS_COCO/"` (See `Prerequisites` below)<br />(5) The checkpoint files of trained models lie in the folder `"./models/"` (You should create this folder manually before training)<br />(6) After inferring procedure, the stylized images will be generated and put in the folder `"./outputs/"`
- For training, you should make sure (2), (3), (4) and (5) are prepared correctly.
- For inferring, you should make sure (1) and (5) are prepared correctly.
- Of course, you can organize all the files and folders as you want, and what you need to do is just modifying the `main.py` file.

## Prerequisites
- [Pre-trained VGG19 network](http://www.vlfeat.org/matconvnet/models/beta16/imagenet-vgg-verydeep-19.mat) (MD5 `8ee3263992981a1d26e73b3ca028a123`) <br/><b>I have provided a convertor in the `tool` folder. It can convert the matlab file into a npz file which is much smaller and easier to process via NumPy.</b> <br/><b>Or simply download my pre-processed</b> [Pre-trained VGG19 network npz format](https://s3-us-west-2.amazonaws.com/wengaoye/imagenet-vgg-19-weights.npz) (MD5 `c7ddd13b12e40033b5031ff43e467065`) <b>The npz format is about 80MB while the mat format is about 550MB.</b><br/>Chinese user can also use BaiduYun to download from [here](http://pan.baidu.com/s/1nv4ZQI1).
- [Microsoft COCO dataset](http://msvocds.blob.core.windows.net/coco2014/train2014.zip)

## Trained Models
I have trained [models](https://s3-us-west-2.amazonaws.com/wengaoye/ten_trained_models.zip) over 10 styles: wave, udnie, escher_sphere, flower, scream, denoised_starry, starry_bright, rain_princess, woman_matisse, mosaic. (You can click the "models" to download)<br/>Chinese user can also use BaiduYun to download from [here](https://pan.baidu.com/s/1i4DLXvZ).

## My Running Environment
<b>Hardware</b>
- CPU: Intel® Core™ i9-7900X (3.30GHz x 10 cores, 20 threads)
- GPU: NVIDIA® Titan Xp (Architecture: Pascal, Frame buffer: 12GB)
- Memory: 32GB DDR4

<b>Operating System</b>
- ubuntu 16.04.03 LTS

<b>Software</b>
- Python 3.6.2
- NumPy 1.13.1
- TensorFlow 1.3.0
- SciPy 0.19.1
- CUDA 8.0.61
- cuDNN 6.0.21

## References
- This project borrowed some ideas and paradigms from Logan Engstrom's [Fast Style Transfer](https://github.com/lengstrom/fast-style-transfer) and Zhiyuan He's [Fast Neural Style Tensorflow](https://github.com/hzy46/fast-neural-style-tensorflow)
- Parts of README formatting were copied from Justin Johnson's [Fast Neural Style](https://github.com/jcjohnson/fast-neural-style) and Zhiyuan He's [Fast Neural Style Tensorflow](https://github.com/hzy46/fast-neural-style-tensorflow)

## Citation
```
  @misc{ye2017fastneuralstyletransfer,
    author = {Wengao Ye},
    title = {Fast Neural Style Transfer},
    year = {2017},
    publisher = {GitHub},
    journal = {GitHub repository},
    howpublished = {\url{https://github.com/elleryqueenhomels/fast-neural-style-transfer}}
  }
```

