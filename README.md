# 🎨 Stable Diffusion & FLUX — AI Image Generation Notebook



## 📌 Project Overview

This Jupyter Notebook demonstrates AI-powered **text-to-image generation** using two cutting-edge diffusion models:

- **Stable Diffusion v1.5** — A fast, open-source model for generating artistic and realistic images from text prompts, running in latent space for efficiency.
- **FLUX.1-dev by Black Forest Labs** — A state-of-the-art, gated diffusion model that requires high-end GPU compute and authorized Hugging Face access.

The notebook covers both fundamental concepts of how diffusion models work and hands-on code for generating images with real prompts.

---

## 🧠 How Stable Diffusion Works (Concepts Covered)

1. **Text-to-Image**: Converts natural language prompts (e.g., *"a falcon in Picasso style"*) into images.
2. **Noise-to-Image Process**: Starts from random noise (like TV static) and iteratively denoises it into a coherent image.
3. **Core Components**: Uses **CLIP** (text understanding), **UNet** (denoising backbone), and **VAE** (image compression/decompression).
4. **Latent Space**: Operates in a compressed representation space — making it faster and less memory-intensive than pixel-space diffusion models.
5. **Open Source**: Weights are publicly available and can be fine-tuned or customized.

---

## 🗂️ Notebook Structure

| Section | Description |
|---|---|
| Install & Imports | Install `diffusers`, import `DiffusionPipeline` |
| Stable Diffusion v1.5 | Load model, send to GPU, generate images |
| Image Prompting | Three example prompts — artistic, realistic, action |
| Advanced: FLUX.1-dev | Load gated FLUX model using HF token |
| Notes on Gated Models | What gated models are and how to gain access |
| Compute Requirements | Paid GPU environment details |

---

## ⚙️ Requirements

### Software
```bash
pip install diffusers torch transformers accelerate
```

### Hardware
| Model | Minimum GPU VRAM | Recommended Environment |
|---|---|---|
| Stable Diffusion v1.5 | 6 GB VRAM | Google Colab Pro (T4 GPU) |
| FLUX.1-dev | 16–24 GB VRAM | RunPod.io / Colab Pro+ (A100) |

> ⚠️ **Free-tier Google Colab and local CPU machines will NOT be sufficient for FLUX.1-dev.**

---

## 🔐 Hugging Face Gated Model Access (FLUX)

FLUX.1-dev is a **gated model** — its weights are restricted and require explicit approval.

**Steps to get access:**
1. Create/log in to your [Hugging Face](https://huggingface.co) account.
2. Visit the [FLUX.1-dev model page](https://huggingface.co/black-forest-labs/FLUX.1-dev).
3. Go to the **Files and Versions** tab and request access.
4. Once approved, generate your HF token from **Settings → Access Tokens**.
5. Set it in the notebook:

```python
import os
os.environ['HF_TOKEN'] = "your_token_here"
```

---

## 🚀 Running the Notebook

### Option 1: Google Colab Pro (Recommended for SD v1.5)
1. Upload the `.ipynb` to [Google Colab](https://colab.research.google.com).
2. Set Runtime → **GPU** (T4 or higher).
3. Run cells sequentially.

### Option 2: RunPod.io (Recommended for FLUX)
1. Create an account at [RunPod.io](https://www.runpod.io).
2. Spin up a GPU pod with at least **24 GB VRAM** (e.g., A100).
3. Upload and run the notebook in the pod's Jupyter environment.

---

## 💡 Example Prompts Used

```python
# Artistic style
pipeline("Image of the falcon in picasso style")

# Photorealistic
pipeline("Image of the falcon which looks like real")

# Dynamic scene
pipeline("Image of the flying falcon with his prey. generate a realistic image")
```

---

## 📦 Models Used

| Model | Source | Access |
|---|---|---|
| `runwayml/stable-diffusion-v1-5` | Hugging Face | Open |
| `black-forest-labs/FLUX.1-dev` | Hugging Face | Gated (requires approval) |

---

## 💳 Paid Tools Required

| Tool | Purpose | Link |
|---|---|---|
| Google Colab Pro | GPU compute for SD v1.5 | [colab.research.google.com](https://colab.research.google.com) |
| RunPod.io | High-VRAM GPU cloud for FLUX | [runpod.io](https://www.runpod.io) |
| Hugging Face Account | Model access & HF token | [huggingface.co](https://huggingface.co) |

---


## 📄 License

This project is for educational purposes. Feel free to use and adapt it for your own learning.

