# Transformer-Based Denoising in Diffusion Models (MNIST)

This project implements a diffusion model for image denoising using the MNIST dataset. It features a custom "Denoiser" network that combines convolutional layers with Transformer self-attention blocks.

## Project Overview
* **Forward Diffusion**: Implements a linear beta schedule over $T=50$ steps to incrementally add noise to images.
* **Denoiser Architecture**: 
    * **Encoder**: Two convolutional layers ($1 \to 32 \to 64$ channels) to extract spatial features.
    * **Transformer Block**: Utilizes a Multi-head self-attention mechanism to capture long-range spatial dependencies.
    * **Decoder**: Mirror-symmetric convolutions ($64 \to 32 \to 1$) to reconstruct the image.

## Performance & Evaluation
* **Training**: 70 epochs using the Adam optimizer and Mean Squared Error (MSE) loss.
* **Metrics**: The model is evaluated using MSE and Structural Similarity Index (SSIM).
* **Results**: Successfully preserves key digit features even at high noise levels, producing smooth reconstructions.
