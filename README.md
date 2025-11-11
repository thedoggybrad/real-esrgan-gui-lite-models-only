# Real-ESRGAN GUI (Lite Models Only)

A cross-platform GUI for image upscaler [Real-ESRGAN](https://github.com/xinntao/Real-ESRGAN) with additional features that uses only lightweight models. Based on [Real-ESRGAN GUI](https://github.com/TransparentLC/realesrgan-gui) which is inspired by [waifu2x-caffe](https://github.com/lltcggie/waifu2x-caffe).

<picture>
    <source media="(prefers-color-scheme:dark)" srcset="https://user-images.githubusercontent.com/47057319/219046059-6611f26b-c558-436e-a1d2-9576d355c2c6.png">
    <img src="https://user-images.githubusercontent.com/47057319/219046017-467f4020-5257-4938-9bfe-b6ab6c65b706.png">
</picture>

## Introduction

This application uses Real-ESRGAN's portable executable file ([Real-ESRGAN-ncnn-vulkan](https://github.com/xinntao/Real-ESRGAN-ncnn-vulkan)) to upscale images with extremely high quality. It is written in Python and provides an user-friendly GUI with Tkinter. 
<br><br>
This specific configuration of Real-ESRGAN was created because my NVIDIA GeForce GT1030 4GB SDDR4 cannot run the more heavy upscaling models.

Available Models:
* 4xLSDIRCompactC3
* digital-art-4x
* realesr-animevideov3-x2
* realesr-animevideov3-x3
* realesr-animevideov3-x4
* RealESRGAN_General_WDN_x4_v3
* RealESRGAN_General_x4_v3
* upscayl-lite-4x

Quick Start：
* ![Windows 10+](https://camo.githubusercontent.com/1b992ebcd3880133edf721523ba59a866b0b8c270ab7a768a49b49b7b73277f4/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f57696e646f77732d31302b2d3036623f6c6f676f3d77696e646f7773) Download the latest `real-ersgan-gui-lite.zip` from Release, extract the archive then launch `realesrgan-gui.exe`.<br>
N.B. Included models are only tested to work on an NVIDIA GeForce GT1030 4GB SDDR4 but should work on a better graphics card. 

## Download Link
[Click here to download](https://github.com/thedoggybrad/real-esrgan-gui-lite-models-only/releases/download/1.0/real-ersgan-gui-lite.zip)

## Features
In addition to the features supported by Real-ESRGAN-ncnn-vulkan, Real-ESRGAN GUI also supports these additional features:

* Upscale to arbitrary size
    * Real-ESRGAN-ncnn-vulkan can only upscale the input image at a fixed 2-4x ratio (depending on the model chosen).
    * Real-ESRGAN GUI uses Real-ESRGAN-ncnn-vulkan to upscale the input image in multiple times, then downsamples the output image to the desired size with general image scaling algorithms.
    * For example, to upscale a 640x360 image to 1600 in width with a 2x model, it will be upscaled twice to 1280x720 and 2560x1440 then downsampled to 1600x900.
    * Lanczos is used by default to downsample the image. Other algorithms are also available.
* Upscale GIF images
    * Split animated GIF into frames and reads their duration. Upscale the frames one by one then merge them into upscaled animated GIF image.
* Drag and drop support
    * Drag and drop image files or directories onto the GUI and the input and output path will be set automatically.
    * The output path will contain a suffix like x4, w1280, h1080 based on the chosen resize mode.
* Dark theme
    * Choose to use light or dark theme according to system settings.
    * The detection is done using [darkdetect](https://github.com/albertosottile/darkdetect).
    * Not available on macOS?
* Multi-language support
    * Simplified and traditional Chinese and English are currently supported.
    * Uses `locale.getdefaultlocale` for language detection.
    * Fallback to English by default if translated text is missing.

## Contributors
[![Contributors](https://contrib.rocks/image?repo=TransparentLC/realesrgan-gui)](https://github.com/TransparentLC/realesrgan-gui/graphs/contributors)
