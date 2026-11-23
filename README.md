# Colab Notebooks

Google Colab 笔记本集合。

## Notebooks

### ComfyUI + FLUX.3 Image Klein (INT8 量化版 & BF16 未量化原版)

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/mugendainayumeatono/colab/blob/main/comfyui_flux3_klein_int8.ipynb)

- **文件**：[`comfyui_flux3_klein_int8.ipynb`](./comfyui_flux3_klein_int8.ipynb)
- **模型来源**：[`black-forest-labs/flux-3-image-klein-comfy`](https://huggingface.co/black-forest-labs/flux-3-image-klein-comfy)（Gated Repo，需在 HuggingFace 同意许可并配置 `HF_TOKEN`）
  - **INT8 量化版**（`PRECISION="int8"`，约 16.5 GB）：`flux3-image-klein[-base]-int8-convrot` + `qwen3vl_4b_int8_convrot` + `qwen3.5_9b_flux3_prompt_upsampler_w4a8` + `flux2-vae`
  - **BF16 未量化原版**（`PRECISION="bf16"`，约 36.5 GB）：`flux3-image-klein[-base]-bf16` + `qwen3vl_4b_bf16` + `qwen3.5_9b_flux3_prompt_upsampler_bf16` + `flux2-vae`
  - 支持在 Cell 4 中自由切换 `PRECISION`（`int8` / `bf16` / `both`）、`MODEL_VARIANT`（`klein` 蒸馏版 / `klein_base` 未蒸馏版 / `both`）与 `UPSAMPLER_PRECISION`（`auto` / `bf16` / `int8_convrot` / `w4a8` / `none`），并自动匹配下载官方工作流（`t2i` / `i2i` / `mi2i`）。
- **推荐运行时**：
  - 未量化 BF16：**A100 (40/80GB, `sm_80`)** 或 **L4 (24GB + 53GB RAM, `sm_89`)**
  - 量化 INT8：**L4 (24GB, `sm_89`)** 或 **A100 (`sm_80`)**（T4 `sm_75` 建议关闭 Prompt Upsampler）
- **公网访问**：内置 `cloudflared` 临时隧道自动映射 `http://127.0.0.1:8188`（默认 `--protocol http2` 走 TCP，避免 Colab 容器 UDP/QUIC 拥塞）。
