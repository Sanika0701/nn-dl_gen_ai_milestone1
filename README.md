# Text-to-Image Generation Pipeline

## 📋 Project Overview

This project implements a complete text-to-image generation pipeline using the COCO dataset and pre-trained models (CLIP + Stable Diffusion). The pipeline converts text prompts into embeddings and generates corresponding images.

## 🎯 Objectives

- Process and preprocess 5,000 COCO image-caption pairs
- Build a baseline text→embedding pipeline using CLIP
- Generate images from text prompts using Stable Diffusion
- Evaluate results using CLIP scores and quality metrics

### Installation

1. Clone this repository:
```bash
git clone https://github.com/YOUR_USERNAME/nndl_gen_ai_milestone1.git
cd nndl_gen_ai_milestone1
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Open the notebook in Google Colab:
   - Upload notebook to Colab
   - Run all cells sequentially

## 📊 Dataset

**COCO (Common Objects in Context) - 2017 Validation Set**
- **Size:** 5,000 images used (from 5K total available)
- **Captions:** 5 captions per image
- **Format:** JPG images + JSON annotations
- **Download:** Automated in notebook (~1GB)

## 🏗️ Architecture

### Models Used

1. **CLIP (Text Encoder)**
   - Model: `openai/clip-vit-base-patch32`
   - Purpose: Convert text prompts to embeddings
   - Output: 77 × 512 dimensional embeddings

2. **Stable Diffusion v1.4**
   - Model: `CompVis/stable-diffusion-v1-4`
   - Purpose: Generate images from text embeddings
   - Components: U-Net + VAE Decoder

### Pipeline Flow

```
Text Prompt → CLIP Tokenizer → Text Embeddings (77×512) 
→ Stable Diffusion U-Net → Latent Image → VAE Decoder → Final Image (512×512)
```

## 🧪 Experiments & Results

### Test Prompts

1. "a dog playing with a ball in the garden"
2. "a bowl of fresh fruit on a table"
3. "a person riding a bicycle in the park"
4. "a cat sitting on a couch"
5. "a beautiful sunset over the ocean"

## 📈 Key Findings

✅ Successfully implemented end-to-end text-to-image pipeline  
✅ CLIP embeddings show proper normalization (mean ≈ 0.12, std ≈ 1.07)  
✅ Generated images demonstrate good text-image alignment  
⚠️ Some fine-grained details (e.g., small objects) occasionally missing  
💡 Future work: Fine-tuning, prompt engineering, newer models (SD v2.1)

## 📚 References

1. COCO Dataset: [https://cocodataset.org/](https://cocodataset.org/)
2. CLIP Paper: [Learning Transferable Visual Models From Natural Language Supervision](https://arxiv.org/abs/2103.00020)
3. Stable Diffusion: [High-Resolution Image Synthesis with Latent Diffusion Models](https://arxiv.org/abs/2112.10752)
4. Hugging Face Diffusers: [https://huggingface.co/docs/diffusers/](https://huggingface.co/docs/diffusers/)

## 📄 License

This project is for academic purposes only.
