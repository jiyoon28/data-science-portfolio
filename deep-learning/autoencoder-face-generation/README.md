# Autoencoder Face Generation

## Project Overview

This project implements end-to-end face generation and editing using deep learning techniques. The pipeline demonstrates Variational Autoencoder (VAE) training on the CelebA dataset, with applications including random face sampling, latent space interpolation, and masked face sharpening using Stable Diffusion.

---

## Pipeline Components

| Stage | Description |
|-------|-------------|
| Data Loading | CelebA dataset streaming with resize, crop, flip, and normalization |
| VAE Architecture | Encoder-decoder with latent space for generative modeling |
| Training | Combined MSE reconstruction loss + KL divergence optimization |
| Random Sampling | Generate new faces from Gaussian prior |
| Latent Interpolation | Smooth morphing between encoded faces |
| Face Sharpening | Masked diffusion enhancement for facial details |

---

## Model Architecture

**Encoder**:
- Four Conv2d layers compressing to 512x8x8 feature map
- Linear layers for mean (mu) and log-variance heads

**Decoder**:
- Linear projection from latent space
- Four ConvTranspose2d layers reconstructing 128x128 images

**Loss Function**: MSE Reconstruction + KL Divergence

---

## Key Results

- **Random Generation**: VAE successfully generates diverse, realistic face samples from Gaussian noise
- **Smooth Interpolation**: Linear blending in latent space produces natural morphing transitions between faces
- **Face Sharpening**: Masked Stable Diffusion Img2Img achieves the sharpest facial details with minimal background artifacts

---

## Project Structure

| File | Description |
|------|-------------|
| autoencoder-face-generation-code.ipynb | Complete implementation notebook |
| autoencoder-face-generation.pdf | Technical report with results |

---

## Technologies Used

- **Language**: Python 3.x
- **Framework**: PyTorch
- **Libraries**: Hugging Face Diffusers, PIL, torchvision
- **Dataset**: CelebA (Celebrity Faces Attributes)
- **Techniques**: Variational Autoencoder, Latent Space Interpolation, Stable Diffusion Img2Img
