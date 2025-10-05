# 🚀 QLoRA-Tex

This project introduces **FormulaFast**, a highly specialized and resource-efficient solution for converting images of mathematical equations directly into accurate **LaTeX** code.

It leverages the powerful **Qwen2-VL-7B-Instruct** Vision Language Model, fine-tuned using the optimized **Unsloth** QLoRA framework.

---

## 🎯 Project Goal: Image-to-LaTeX Code Generation

The core task is $\text{Mathematical OCR}$: extracting the precise structured $\LaTeX$ code from an image, aiming for high fidelity and low error rates.

## ⚙️ Key Technology Stack

| Feature | Description | Benefit/Goal |
| :--- | :--- | :--- |
| **Base Model** | **Qwen2-VL-7B-Instruct** (Multimodal VLM) | Provides strong visual and linguistic foundation for complex formulas. |
| **Fine-Tuning** | **Unsloth QLoRA (4-bit)** | Achieves **2x speed** and **70% less VRAM** usage, enabling training on a standard T4 GPU. |
| **Adapter Size** | LoRA Rank $r=16$ | Only $\sim 1\%$ of model weights are updated for efficiency. |
| **Dataset** | `unsloth/Latex_OCR` | Comprehensive training set for diverse equation styles. |

---

## 📈 Initial Performance Metrics

These metrics were recorded after a brief, 50-step fine-tuning run on the training dataset and evaluated against 100 samples from the test set.

| Metric | Value | Interpretation |
| :--- | :--- | :--- |
| **Total Samples Evaluated** | 100 | The size of the held-out test set evaluated. |
| **Average Normalized Edit Distance (NED)** | `0.1860` | The character-level error rate. The goal is closer to `0.00`. |
| **Average Character Accuracy** | `81.40%` | $\mathbf{81.40\%}$ of generated characters/tokens match the ground truth. |

***

## 💻 Sample Inference and Code

### Ground Truth $\LaTeX$ Example:

```latex
D _ { \mu } ^ { \alpha \beta } \bar { A } _ { \mu } ^ { \alpha \beta } = 0
