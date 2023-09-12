# Underwater image improvement and reef segmentation preliminary work

---

<p align="center">
<img src="assets/CIIC_logo_v2.png" width="1000px"/>
</p>

---

This repository stores the preliminary work made to explores image enhancement methods for underwater imagery and reef segmentation. 

## 1. Image Enhancement

Image enhancement methods are used to improve the quality of underwater images, which are often degraded by the effects of scattering and absorption. These methods can be classified into two categories: classical image enhancement algorithms and deep learning-based models. Classical algorithms are based on the Retinex theory, which aims to restore the original color of an image by separating the illumination and reflectance components. Deep learning-based models, on the other hand, employ convolutional neural networks to enhance underwater images.
We evaluate the performance of four image enhancement algorithms on our underwater image dataset captured in Leixoes bay, Portugal.

### 1.1 Tested Models

| Model      | Description                                                                                                                    |
|------------|--------------------------------------------------------------------------------------------------------------------------------|
| **MSRCP**  | MSRCP is an image enhancement algorithm that incorporates multi-scale retinex processing with color priors. It excels in improving overall image quality, addressing issues like illumination and color balance.  |
| **MSRCR**  | MSRCR is another image enhancement method that employs multi-scale retinex processing with a focus on color restoration. It excels in enhancing color fidelity and sharpness in images, suitable for various applications. |
| **UWCNN**  | UWCNN is a convolutional neural network-based model designed for enhancing underwater color images. It utilizes deep learning techniques to enhance image quality and visibility in underwater environments.  |
| **Waternet**| Waternet is a specialized algorithm for enhancing underwater images. It's designed to counter the adverse effects of underwater conditions, such as scattering and low light, resulting in clearer and more visually appealing underwater images. |


## 1.2 Table of Performance Metrics for Image Enhancement Algorithms

| Model              | UIQM             | UCIQE            |
|----------------------|------------------|------------------|
| Without Treatment    | $0.75 \pm 0.66$  | $18.06 \pm 3.39$ | 
| **MSRCP**            | **$6.56 \pm 1.36$**  | $29.30 \pm 0.38$ | 
| **MSRCR**            | $6.20 \pm 1.22$  | **$30.14 \pm 0.50$**  | 
| **UWCNN**            | $1.74 \pm 0.70$  | $22.51 \pm 3.11$ | 
| **Waternet**         | $2.13 \pm 0.68$  | $25.32 \pm 0.94$ |

- **UIQM** (Universal Image Quality Metric).
- **UCIQE** (Universal Color Image Quality Evaluation) 

### 1.3 Key Takeaways

The evaluation of these models in terms of performance metrics:
* MSRCR has the best performance in terms of UCIQE, while MSRCP has the best performance in terms of UIQM.
* UWCNN the worst performance in terms of UIQM and UCIQE.
* WaterNet has competitive performance in terms of UCIQE.

Qualitative evaluation of these models:
* MSRCP does not perform well in terms of color restoration.
* Waternet has images seem more natural and visually appealing.
* UWCNN has images lack sharpness and color fidelity.


## 2. Reef Segmentation

Reef segmentation is a challenging task due to the complex nature of reef environments. The presence of various organisms, such as corals, sponges, and algae, makes it difficult to distinguish between them. In addition, the presence of sand and other debris can further complicate the segmentation process. We evaluate the performance of three semantic segmentation models on our reef image dataset captured in Leixoes bay, Portugal.

### 2.1 Tested Models

**DeepLabV3+**: DeepLabV3+ is a state-of-the-art semantic segmentation model that employs a deep convolutional neural network to perform pixel-wise classification. It is particularly effective in segmenting objects in images with complex backgrounds.

**U-Net Variants**: U-Net is a convolutional neural network-based model that is widely used in biomedical image segmentation. It is designed to perform pixel-wise classification by combining the encoder and decoder networks.

**Swin Unet**: Swin Unet is a semantic segmentation model that employs a transformer-based architecture. It is designed to perform pixel-wise classification by combining the encoder and decoder networks.


| Model           | Description                                                                                                                |
|-----------------|----------------------------------------------------------------------------------------------------------------------------|
| **DeepLabV3+**  | DeepLabV3+ is a semantic segmentation model that utilizes a deep convolutional neural network for pixel-wise classification. It excels at segmenting objects in images with complex backgrounds. |
| **U-Net Variants** | U-Net is a convolutional neural network-based model widely used in biomedical image segmentation. It combines encoder and decoder networks for pixel-wise classification. |
| **Swin Unet**   | Swin Unet is a semantic segmentation model using a transformer-based architecture. It combines encoder and decoder networks for pixel-wise classification. |


### 2.2 Preliminary Results

| Model              | Mean IoU             | 
|----------------------|------------------|
| **DeepLabV3+**            | - |
| **Swin Unet**            | ~ $0.80$   |
| **U-Net V0**            | ~ $0.56$  |
| **U-Net V2**            | ~ $0.82$  |

