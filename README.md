<div align="center">


<img src="images/logo.png" width="130" alt="EyeVQA Logo">

# EyeVQA: Benchmarking Ophthalmic Vision-Language Models from Recognition to Spatial Grounding

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

Gujie Shao<sup>*1</sup>, Zixun Xie<sup>*2</sup>, Xuechun Xing<sup>*1</sup>, Ruixiang Wang<sup>*1</sup>, Ziyun Lan<sup>1</sup>,  
Yanlin Qi<sup>3</sup>, Gangyi Zhang<sup>1</sup>, Yuxin Yang<sup>1</sup>, Dawei Li<sup>†2</sup>, Haiming Tang<sup>†1,4</sup>

<br>
(<sup>*</sup>Equal contribution, <sup>†</sup>Corresponding authors)
</div>


## 🌟 Highlights
- **Comprehensive Benchmark Scale**: Unifies **21 public ophthalmic datasets** into **20,000 clinically grounded QA pairs** covering 6 disease groups.
- **Deterministic & Hallucination-Free**: Gold answers and spatial targets are strictly extracted from expert-verified labels, masks, and landmarks.
- **Multi-Image Comparative Reasoning**: Incorporates 10,344 four-panel composites, making **44.5% (8,902 questions)** evaluate relational and ordinal reasoning across multiple images.
- **Fine-Grained Spatial Grounding**: Beyond categorical diagnosis, explicitly assesses **Point Location (PL)** and **Bounding Box (BB)** prediction.

## 📰 News
- **[2026-08]** 🎉 **EyeVQA** has been accepted to the **MICCAI 2026 Workshop CREATE**!


## 🔍 Overview of EyeVQA

<div align="center">
  <img src="images/figure1.png" width="95%" alt="Overview of the EyeVQA benchmark">
  <p><em>Figure 1: Overview of the EyeVQA benchmark, showcasing the 7 question formats spanning categorical diagnosis, multi-image relational reasoning, and coordinate-based spatial grounding.</em></p>
</div>


## 📈 Dataset Statistics & Analysis

<div align="center">
  <img src="images/figure2.png" width="95%" alt="Dataset statistics of EyeVQA">
  <p><em>Figure 2: Dataset overview of EyeVQA: (a) distribution of question types; (b) question length distribution by type; (c) question-type composition across disease groups; (d) clinical vocabulary frequency.</em></p>
</div>

## 📊 Leaderboard

### Benchmark Performance Summary

| Model | Type | Total | DR | GL | PM | MD | MU | OT | SC | MS | VS | TF | RK | PL | BB |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| `Intern-S2-Preview-397B` | Science | **62.8** | **63.2** | **57.9** | **57.9** | **73.4** | **62.5** | 67.7 | **60.2** | 63.0 | **51.6** | **76.2** | 55.8 | **70.7** | 45.5 |
| `Intern-S2-Preview-35B` | Science | 59.3 | 60.0 | 57.1 | 55.6 | 60.8 | 60.4 | 68.1 | 60.1 | **63.3** | 50.5 | 70.5 | 59.1 | 45.2 | 49.4 |
| `Gemini-3.1-Flash-Lite` | Closed | 57.0 | 55.7 | 49.5 | 53.0 | 66.8 | 54.1 | **73.4** | 53.4 | 58.6 | 44.3 | 67.3 | 54.6 | 56.5 | **58.1** |
| `Gemini-3.5-Flash-Lite` | Closed | 55.9 | 55.2 | 55.4 | 48.4 | 69.5 | 53.3 | 56.5 | 53.1 | 58.9 | 45.1 | 70.2 | 49.8 | 65.3 | 27.8 |
| `Intern-S1-Pro` | Science | 54.1 | 58.7 | 51.9 | 51.9 | 58.6 | 54.0 | 44.4 | 49.6 | 59.0 | 44.5 | 70.2 | **60.0** | 50.7 | 17.0 |
| `MedGemma-4B-IT` | Medical | 51.5 | 62.5 | 52.2 | 47.2 | 48.7 | 57.0 | 30.1 | 47.6 | 53.6 | 41.9 | 71.1 | 58.1 | 46.5 | 6.2 |
| `Lingshu-7B` | Medical | 50.9 | 58.6 | 46.3 | 48.6 | 52.2 | 47.7 | 43.8 | 53.0 | 59.5 | 45.0 | 61.8 | 56.8 | 35.1 | 19.2 |
| `MedGemma-1.5-4B-IT` | Medical | 49.9 | 59.8 | 53.3 | 40.3 | 51.0 | 56.0 | 31.1 | 48.7 | 57.8 | 40.8 | 64.6 | 50.0 | 51.3 | 7.5 |
| `GLM-4.1V-Thinking-Flash` | Open | 49.5 | 49.1 | 46.3 | 46.9 | 55.5 | 46.6 | 55.7 | 43.1 | 51.2 | 38.5 | 60.3 | 57.3 | 50.6 | 34.5 |
| `Qwen3-VL-8B-Instruct` | Open | 48.9 | 46.9 | 50.8 | 48.5 | 40.7 | 47.5 | 64.7 | 44.7 | 58.8 | 39.4 | 60.1 | 49.5 | 29.0 | 46.2 |
| `Qwen2.5-VL-7B-Instruct` | Open | 47.1 | 45.5 | 49.4 | 48.4 | 51.1 | 54.9 | 34.6 | 45.2 | 58.2 | 44.2 | 54.4 | 54.8 | 44.6 | 7.3 |
| `GLM-4.6V-Flash` | Open | 45.6 | 44.8 | 44.0 | 44.6 | 45.2 | 38.5 | 57.3 | 37.6 | 54.0 | 36.4 | 51.6 | 57.4 | 27.9 | 51.8 |
| `Qwen2.5-VL-3B-Instruct` | Open | 41.0 | 44.4 | 34.4 | 43.5 | 38.2 | 54.3 | 39.0 | 39.2 | 51.2 | 39.7 | 45.9 | 52.1 | 23.2 | 20.1 |
| `GLM-4V-Flash` | Open | 39.3 | 37.5 | 45.0 | 41.6 | 41.5 | 35.7 | 25.4 | 37.1 | 48.9 | 31.8 | 42.1 | 53.2 | 51.3 | 4.0 |

> *All metric scores are linearly normalized to [0, 100].*

## 📁 Dataset Preparation & Licensing

Due to licensing restrictions and data governance policies, some original ophthalmic datasets do not permit direct redistribution. Consequently:

- **What We Provide**: This repository contains the complete benchmark metadata, standardized QA pairs, and source image URLs/identifiers
- **What You Need to Do**: Users should download the raw datasets directly from their official repositories.


## 📑 Citation

If you find EyeVQA useful in your research, please cite our work:

```bibtex
@inproceedings{shao2026eyevqa,
  title={EyeVQA: Benchmarking Ophthalmic Vision-Language Models from Recognition to Spatial Grounding},
  author={Shao, Gujie and Xie, Zixun and Xing, Xuechun and Wang, Ruixiang and Lan, Ziyun and Qi, Yanlin and Zhang, Gangyi and Yang, Yuxin and Li, Dawei and Tang, Haiming},
  booktitle={MICCAI 2026 Workshop on Clinical-driven Robotics and Embodied AI Technology (CREATE)},
  series={LNCS},
  publisher={Springer},
  year={2026}
}
```

---

## 📬 Contact
For questions or benchmark inquiries, please contact `haiming@comp.nus.edu.sg` or `lidawei@pku.edu.cn`.
