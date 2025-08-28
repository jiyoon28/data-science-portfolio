# autoencoder-face-generation

This single-notebook pipeline implements end-to-end face generation and editing using PyTorch and Hugging Face Diffusers:

1. **Data Loading & Transforms**

   - Streams the CelebA dataset, applies resize, crop, flip, tensor conversion, and normalization.

2. **Variational Autoencoder (VAE)**

   - Encoder: four Conv2d layers down to a 512×8×8 feature map.
   - Latent heads: linear layers for μ and log-variance.
   - Decoder: linear projection + four ConvTranspose2d layers back to 128×128 images.

3. **Training Loop**

   - Optimizes combined MSE reconstruction loss + KL divergence over multiple epochs and mini-batches.
   - Logs per-batch and per-epoch Total, Recon, and KLD losses.

4. **Random Sampling**

   - Samples from Gaussian prior N(0,I), decodes to faces, and visualizes in an 8×8 grid.

5. **Latent-Space Interpolation**

   - Linearly blends between two encoded face vectors over N steps and decodes each to show smooth morphing.

6. **Masked Face Sharpening**
   - Generates a central-face mask and applies:
     - **UnsharpMask** via PIL for quick sharpening.
     - **Stable Diffusion Img2Img** only inside the mask for stronger detail.

The masked diffusion sharpening achieves the most visually crisp facial details with minimal background change.
