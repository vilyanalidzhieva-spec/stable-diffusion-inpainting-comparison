# Stable Diffusion Inpainting Comparison

A Streamlit application that uses Stable Diffusion Inpainting 
to regenerate a selected area of an image and compares the 
generated result with an undamaged original using PSNR and SSIM.

## How it works

1. Upload a damaged image.
2. Upload the undamaged original.
3. Paint the damaged area on the canvas.
4. Enter a prompt for Stable Diffusion.
5. Run generation.
6. Compare the generated result with the original using PSNR and SSIM.

## Model

The application uses:

```text
sd-legacy/stable-diffusion-inpainting
```

This is a latent diffusion model for text-guided image inpainting.

## Installation

```bash
python3 -m venv sd-env
source sd-env/bin/activate
python -m pip install --upgrade pip
python -m pip install streamlit torch diffusers transformers accelerate scikit-image pillow numpy streamlit-drawable-canvas
```

## Run

```bash
python -m streamlit run sd_compare.py
```

Then open:

```text
http://localhost:8501
```

## Metrics

- **Masked PSNR** compares the generated area with the original only inside the painted mask.
- **Full-image PSNR** compares the entire generated image with the original.
- **Full-image SSIM** measures structural similarity between the generated image and the original.

Low scores can occur when Stable Diffusion generates a plausible but non-identical restoration.

## Important note

This application is an image-restoration experiment. 
Generated content is not a verified historical reconstruction.