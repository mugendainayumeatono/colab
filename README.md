# Colab Notebooks

Google Colab 笔记本集合。

## Notebooks

### ComfyUI + FLUX.3 Image Klein (INT8 ConvRot)

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/mugendainayumeatono/colab/blob/main/comfyui_flux3_klein_int8.ipynb)

- **文件**：[`comfyui_flux3_klein_int8.ipynb`](./comfyui_flux3_klein_int8.ipynb)
- **模型来源**：[`black-forest-labs/flux-3-image-klein-comfy`](https://huggingface.co/black-forest-labs/flux-3-image-klein-comfy)
  - `diffusion_models/flux3-image-klein-int8-convrot.safetensors`
  - `text_encoders/qwen3vl_4b_int8_convrot.safetensors`
  - `text_encoders/qwen3.5_9b_flux3_prompt_upsampler_w4a8.safetensors`（可选）
  - `vae/flux2-vae.safetensors`
- **推荐运行时**：Google Colab **L4 (24GB, `sm_89`)** 或 **A100 (`sm_80`)**（支持 W4A8 硬件加速；T4 `sm_75` 建议关闭 Prompt Upsampler）。
- **公网访问**：内置 `cloudflared` 临时隧道自动映射 `http://127.0.0.1:8188`。
