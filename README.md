# FiNE: Filtering and Improving Noisy Data Elaborately with Large Language Models

[![Paper — NAACL 2025](https://img.shields.io/badge/Paper-NAACL%202025-blue)](https://aclanthology.org/2025.naacl-long.437/)
[![DOI](https://img.shields.io/badge/DOI-10.18653%2Fv1%2F2025.naacl--long.437-1f6feb)](https://doi.org/10.18653/v1/2025.naacl-long.437)
[![Status](https://img.shields.io/badge/Status-Code%20Release%20in%20Progress-orange)](#-repository-status)
[![License](https://img.shields.io/badge/License-Apache--2.0-blue)](LICENSE)

Official repository for the NAACL 2025 long paper:

FiNE: Filtering and Improving Noisy Data Elaborately with Large Language Models  
Authors: Junliang He, Ziyue Fan, Shaohui Kuang, Li Xiaoqing, Kai Song, Yaqian Zhou, Xipeng Qiu  
DOI: 10.18653/v1/2025.naacl-long.437

- Paper page: https://aclanthology.org/2025.naacl-long.437/
- PDF: https://aclanthology.org/2025.naacl-long.437.pdf

---

## Overview

Large Language Models (LLMs) are powered by data—but open-source instruction datasets are often noisy, inconsistent, or misaligned with user preferences. FiNE is a method that leverages LLMs to perform refined filtering and improvement of training data. Rather than relying on coarse heuristics or one-off augmentation, FiNE orchestrates LLM-driven checks and edits that elevate data integrity at scale.

In experiments training Yi-1.5-9B, data processed with FiNE significantly closes the gap to the open-source chat version on AlignBench (from 1.08 to 0.35) and achieves +8.45 on HalluQA compared to the open-source chat baseline.

### Why FiNE

- LLM-driven, fine-grained data refinement for instruction datasets.
- Practical pipeline: combine filtering with targeted improvement rather than either alone.
- Demonstrated gains on downstream benchmarks (AlignBench, HalluQA) with Yi-1.5-9B.

---

## What's inside this repository

This repo serves as the public home for FiNE:

- Paper links and citation information.
- Release point for code, scripts, and data resources (including FiNE-related instruction datasets).
- FiNE-Alpaca is now open-sourced under `./FiNE-alpaca/`.

We are preparing cleaned datasets, reproduction scripts, and documentation to help you apply FiNE to your own data pipelines. See the status and roadmap below.

---

## FiNE-Alpaca

FiNE-Alpaca is our open-sourced resource that applies the FiNE methodology to Alpaca-style instruction data. It aims to provide higher-quality training data and reusable prompts/pipeline components. Please visit `./FiNE-alpaca/` for code and resources. Usage commands will be added as they become available—refer to that directory for notes and updates.

---

## Getting started

Core FiNE pipeline code and additional datasets are being organized for release. FiNE-Alpaca is available now at `./FiNE-alpaca/`. In the meantime:

- Read the paper for the full method and experimental setup:
  - PDF: https://aclanthology.org/2025.naacl-long.437.pdf
- Watch this repository to be notified when code and datasets are published.
- Open an issue if you have questions about applying FiNE in your setting or want early guidance.

### Anticipated contents (coming soon)

- FiNE pipeline scripts and configuration.
- Data validation and LLM-based refinement components.
- Example recipes for cleaning and improving common instruction datasets.
- Reproduction notes for Yi-1.5-9B experiments (AlignBench, HalluQA).

---

## Reproducibility notes

- Benchmarks: AlignBench, HalluQA.
- Model: Yi-1.5-9B (open-source chat version as baseline; FiNE-improved training data for our model).
- Metrics and comparisons follow the paper’s protocol. Detailed scripts and exact data versions will be released here.

---

## Citation

If you find FiNE helpful, please cite our NAACL 2025 paper:

```bibtex
@inproceedings{he-etal-2025-fine,
    title = "{F}i{NE}: Filtering and Improving Noisy Data Elaborately with Large Language Models",
    author = "He, Junliang  and
      Fan, Ziyue  and
      Kuang, Shaohui  and
      Xiaoqing, Li  and
      Song, Kai  and
      Zhou, Yaqian  and
      Qiu, Xipeng",
    editor = "Chiruzzo, Luis  and
      Ritter, Alan  and
      Wang, Lu",
    booktitle = "Proceedings of the 2025 Conference of the Nations of the Americas Chapter of the Association for Computational Linguistics: Human Language Technologies (Volume 1: Long Papers)",
    month = apr,
    year = "2025",
    address = "Albuquerque, New Mexico",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2025.naacl-long.437/",
    doi = "10.18653/v1/2025.naacl-long.437",
    pages = "8686--8707",
    ISBN = "979-8-89176-189-6",
    abstract = "Data is the lifeblood of large language models (LLMs). While the quantity of open-source data available for training LLMs is substantial, its integrity often falls short. For instance, the open-source chat version of Yi-1.5-9B scores 5.20 on AlignBench, while the Chinese Alpaca-GPT4 version scores 4.12. This discrepancy makes it challenging for developers to create models that excel in downstream tasks and instruction following. Therefore, it is essential to improve data integrity. Currently, there are two mainstream methods for enhancing data integrity: data filtering and data augmentation. Due to the labor-intensive and time-consuming nature of performing these tasks manually, some of these efforts are now being undertaken by LLMs, owing to their high alignment with human preferences. However, we have found that performing data filtering or data augmentation with LLMs has limited effectiveness in improving data integrity. In this work, we propose FiNE (\\textbf{F}iltering and \\textbf{I}mproving \\textbf{N}oisy data \\textbf{E}laborately), a method that performs refined filtering and improvement of training data with LLMs. Using the data obtained through our method to train Yi-1.5-9B, the performance gap on AlignBench between our model and the open-source chat version is reduced from 1.08 to 0.35. Additionally, on HalluQA, our model surpasses the open-source chat version by 8.45."
}
```

---

## 中文简介

FiNE 是一种面向指令数据的精细化“过滤 + 改进”方法：借助大语言模型（LLM）对数据进行质量筛查、问题定位与有针对性的修复，从而系统性提升数据完整性与一致性。与仅做过滤或仅做增强相比，FiNE 通过联动的流程更有效地提升训练数据的可用性。

在 Yi-1.5-9B 的训练中，使用 FiNE 处理后的数据显著缩小与开源聊天版在 AlignBench 上的差距（从 1.08 降至 0.35），并在 HalluQA 上相对开源聊天版取得 +8.45 的提升。

我们正在整理代码、数据与复现脚本，并将在本仓库持续发布更新。FiNE-Alpaca 已开源，代码与资源位于本仓库的 `FiNE-alpaca/` 目录。

---

## 🤝 Community & Support

- Questions or ideas? Please open an issue: https://github.com/jlhe2000/FiNE/issues
- Pull requests are welcome once the initial code release is available.

---

## 📌 Repository Status

- Code release: in progress. This repository currently includes paper links and a directory for available/open-sourced resources.
- FiNE-Alpaca: open-sourced at `./FiNE-alpaca/`.
- Roadmap: dataset release and pipeline scripts are planned; watch the repo for updates.

---

## 📄 License

This repository is licensed under the Apache License, Version 2.0. See [LICENSE](LICENSE) for details.
