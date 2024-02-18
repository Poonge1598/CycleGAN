# CycleGAN for Apple and Orange Image Translation

## Project Overview

This project utilizes a CycleGAN architecture to perform image-to-image translation between apples and oranges. CycleGANs allow for this transformation without needing paired images, making it an ideal choice for tasks where collecting corresponding images between two domains is impractical.

## Objective

The primary goal is to learn the mapping between apple images and orange images such that given an image of an apple, the model can generate a corresponding image of an orange, and vice versa, while preserving the context and overall structure of the original image.

## Dataset

The dataset comprises two sets of images:
- **Apples**: A collection of various apple images.
- **Oranges**: A collection of various orange images.

These images are unpaired, with varying backgrounds and compositions.

## Model Architecture

CycleGAN consists of two generators and two discriminators:
- **Generators**:
  - `G_XtoY`: Translates images from domain X (apples) to domain Y (oranges).
  - `G_YtoX`: Translates images from domain Y (oranges) to domain X (apples).
- **Discriminators**:
  - `D_X`: Discriminates between real and generated images in domain X (apples).
  - `D_Y`: Discriminates between real and generated images in domain Y (oranges).

## Loss Functions

- **Adversarial Loss**: Ensures generated images are indistinguishable from real images in each domain.
- **Cycle Consistency Loss**: Ensures that translating an image to another domain and back again will result in the original image.
- **Identity Loss**: Encourages the generator to be an identity function when real images of the target domain are provided.
- **Discriminator Loss**: Ensures discriminators can distinguish between real and generated images. This loss encourages discriminators to assign high scores to real images and low scores to fake images.

## Training

Training involves alternating updates to the generators and discriminators with the following steps:
1. Generate fake images using both generators.
2. Update discriminators using both real and generated images.
3. Compute cycle consistency and identity losses.
4. Update generators using the combined losses.

## Results

The model successfully learns to translate between apple and orange images, preserving the original image's context and structure. Sample results demonstrate the model's ability to handle various apple and orange types, lighting conditions, and compositions.

## Conclusion

This CycleGAN project showcases the potential of unpaired image-to-image translation for applications in style transfer, domain adaptation, and data augmentation. The ability to transform apples to oranges and vice versa without paired training data opens up new avenues for creative and practical image manipulation.
