<div align="center">
  <img src="./assets/dolphin.png" width="300">
</div>

<div align="center">
  <a href="https://arxiv.org/abs/2505.14059">
    <img src="https://img.shields.io/badge/Paper-arXiv-red">
  </a>
  <a href="https://huggingface.co/ByteDance/Dolphin">
    <img src="https://img.shields.io/badge/HuggingFace-Dolphin-yellow">
  </a>
  <a href="https://modelscope.cn/models/ByteDance/Dolphin">
    <img src="https://img.shields.io/badge/ModelScope-Dolphin-purple">
  </a>
  <a href="https://huggingface.co/spaces/ByteDance/Dolphin">
    <img src="https://img.shields.io/badge/Demo-Dolphin-blue">
  </a>
  <a href="https://github.com/bytedance/Dolphin">
    <img src="https://img.shields.io/badge/Code-Github-green">
  </a>
  <a href="https://opensource.org/licenses/MIT">
    <img src="https://img.shields.io/badge/License-MIT-lightgray">
  </a>
  <br>
</div>

<br>

<div align="center">
  <img src="./assets/demo.gif" width="800">
</div>

# Dolphin: Document Image Parsing via Heterogeneous Anchor Prompting
# Dolphin: 基于异构锚点提示的文档图像解析

Dolphin (**Do**cument Image **P**arsing via **H**eterogeneous Anchor Prompt**in**g) is a novel multimodal document image parsing model following an analyze-then-parse paradigm. This repository contains the demo code and pre-trained models for Dolphin.

Dolphin（**Do**cument Image **P**arsing via **H**eterogeneous Anchor Prompt**in**g）是一个创新的多模态文档图像解析模型，采用"分析-解析"的两阶段范式。本仓库包含Dolphin的演示代码和预训练模型。

## 📑 Overview | 概述

Document image parsing is challenging due to its complexly intertwined elements such as text paragraphs, figures, formulas, and tables. Dolphin addresses these challenges through a two-stage approach:

由于文档图像中文本段落、图表、公式和表格等元素的复杂交织，文档图像解析具有挑战性。Dolphin通过两阶段方法解决这些挑战：

1. **🔍 Stage 1**: Comprehensive page-level layout analysis by generating element sequence in natural reading order
2. **🧩 Stage 2**: Efficient parallel parsing of document elements using heterogeneous anchors and task-specific prompts

1. **🔍 第一阶段**：通过按自然阅读顺序生成元素序列进行全面的页面级布局分析
2. **🧩 第二阶段**：使用异构锚点和任务特定提示高效并行解析文档元素

<div align="center">
  <img src="./assets/framework.png" width="680">
</div>

Dolphin achieves promising performance across diverse page-level and element-level parsing tasks while ensuring superior efficiency through its lightweight architecture and parallel parsing mechanism.

Dolphin在多样化的页面级和元素级解析任务中取得了优异的性能，同时通过其轻量级架构和并行解析机制确保了卓越的效率。

## 🚀 Demo | 演示
Try our demo on [Demo-Dolphin](http://115.190.42.15:8888/dolphin/).

在 [Demo-Dolphin](http://115.190.42.15:8888/dolphin/) 上试用我们的演示。

## 📅 Changelog | 更新日志
- 🔥 **2025.06.13** Added multi-page PDF document parsing capability.
- 🔥 **2025.05.21** Our demo is released at [link](http://115.190.42.15:8888/dolphin/). Check it out!
- 🔥 **2025.05.20** The pretrained model and inference code of Dolphin are released.
- 🔥 **2025.05.16** Our paper has been accepted by ACL 2025. Paper link: [arXiv](https://arxiv.org/abs/2505.14059).

- 🔥 **2025.06.13** 新增多页PDF文档解析功能。
- 🔥 **2025.05.21** 我们的演示已在 [链接](http://115.190.42.15:8888/dolphin/) 发布。快来体验吧！
- 🔥 **2025.05.20** Dolphin的预训练模型和推理代码已发布。
- 🔥 **2025.05.16** 我们的论文已被ACL 2025接收。论文链接：[arXiv](https://arxiv.org/abs/2505.14059)。

## 🛠️ Installation | 安装

1. Clone the repository:
   ```bash
   git clone https://github.com/ByteDance/Dolphin.git
   cd Dolphin
   ```

1. 克隆仓库：
   ```bash
   git clone https://github.com/ByteDance/Dolphin.git
   cd Dolphin
   ```

2. Install the dependencies:
   ```bash
   pip install -r requirements.txt
   ```

2. 安装依赖：
   ```bash
   pip install -r requirements.txt
   ```

3. Download the pre-trained models using one of the following options:

3. 使用以下选项之一下载预训练模型：

   **Option A: Original Model Format (config-based)**
   
   Download from [Baidu Yun](https://pan.baidu.com/s/15zcARoX0CTOHKbW8bFZovQ?pwd=9rpx) or [Google Drive](https://drive.google.com/drive/folders/1PQJ3UutepXvunizZEw-uGaQ0BCzf-mie?usp=sharing) and put them in the `./checkpoints` folder.

   **选项A：原始模型格式（基于配置文件）**
   
   从 [百度网盘](https://pan.baidu.com/s/15zcARoX0CTOHKbW8bFZovQ?pwd=9rpx) 或 [Google Drive](https://drive.google.com/drive/folders/1PQJ3UutepXvunizZEw-uGaQ0BCzf-mie?usp=sharing) 下载，并将其放在 `./checkpoints` 文件夹中。

   **Option B: Hugging Face Model Format**
   
   Visit our Huggingface [model card](https://huggingface.co/ByteDance/Dolphin), or download model by:
   
   ```bash
   # Download the model from Hugging Face Hub
   git lfs install
   git clone https://huggingface.co/ByteDance/Dolphin ./hf_model
   # Or use the Hugging Face CLI
   huggingface-cli download ByteDance/Dolphin --local-dir ./hf_model
   ```

   **选项B：Hugging Face模型格式**
   
   访问我们的Huggingface [模型卡片](https://huggingface.co/ByteDance/Dolphin)，或通过以下方式下载模型：
   
   ```bash
   # 从Hugging Face Hub下载模型
   git lfs install
   git clone https://huggingface.co/ByteDance/Dolphin ./hf_model
   # 或使用Hugging Face CLI
   huggingface-cli download ByteDance/Dolphin --local-dir ./hf_model
   ```

## ⚡ Inference | 推理

Dolphin provides two inference frameworks with support for two parsing granularities:
- **Page-level Parsing**: Parse the entire document page into a structured JSON and Markdown format
- **Element-level Parsing**: Parse individual document elements (text, table, formula)

Dolphin提供两个推理框架，支持两种解析粒度：
- **页面级解析**：将整个文档页面解析为结构化的JSON和Markdown格式
- **元素级解析**：解析单个文档元素（文本、表格、公式）

### 📄 Page-level Parsing | 页面级解析

#### Using Original Framework (config-based) | 使用原始框架（基于配置文件）

```bash
# Process a single document image
python demo_page.py --config ./config/Dolphin.yaml --input_path ./demo/page_imgs/page_1.jpeg --save_dir ./results

# Process a single document pdf
python demo_page.py --config ./config/Dolphin.yaml --input_path ./demo/page_imgs/page_6.pdf --save_dir ./results

# Process all documents in a directory
python demo_page.py --config ./config/Dolphin.yaml --input_path ./demo/page_imgs --save_dir ./results

# Process with custom batch size for parallel element decoding
python demo_page.py --config ./config/Dolphin.yaml --input_path ./demo/page_imgs --save_dir ./results --max_batch_size 8
```

```bash
# 处理单个文档图像
python demo_page.py --config ./config/Dolphin.yaml --input_path ./demo/page_imgs/page_1.jpeg --save_dir ./results

# 处理单个文档PDF
python demo_page.py --config ./config/Dolphin.yaml --input_path ./demo/page_imgs/page_6.pdf --save_dir ./results

# 处理目录中的所有文档
python demo_page.py --config ./config/Dolphin.yaml --input_path ./demo/page_imgs --save_dir ./results

# 使用自定义批次大小进行并行元素解码
python demo_page.py --config ./config/Dolphin.yaml --input_path ./demo/page_imgs --save_dir ./results --max_batch_size 8
```

#### Using Hugging Face Framework | 使用Hugging Face框架

```bash
# Process a single document image
python demo_page_hf.py --model_path ./hf_model --input_path ./demo/page_imgs/page_1.jpeg --save_dir ./results

# Process a single document pdf
python demo_page_hf.py --model_path ./hf_model --input_path ./demo/page_imgs/page_6.pdf --save_dir ./results

# Process all documents in a directory
python demo_page_hf.py --model_path ./hf_model --input_path ./demo/page_imgs --save_dir ./results

# Process with custom batch size for parallel element decoding
python demo_page_hf.py --model_path ./hf_model --input_path ./demo/page_imgs --save_dir ./results --max_batch_size 16
```

```bash
# 处理单个文档图像
python demo_page_hf.py --model_path ./hf_model --input_path ./demo/page_imgs/page_1.jpeg --save_dir ./results

# 处理单个文档PDF
python demo_page_hf.py --model_path ./hf_model --input_path ./demo/page_imgs/page_6.pdf --save_dir ./results

# 处理目录中的所有文档
python demo_page_hf.py --model_path ./hf_model --input_path ./demo/page_imgs --save_dir ./results

# 使用自定义批次大小进行并行元素解码
python demo_page_hf.py --model_path ./hf_model --input_path ./demo/page_imgs --save_dir ./results --max_batch_size 16
```

### 🧩 Element-level Parsing | 元素级解析

#### Using Original Framework (config-based) | 使用原始框架（基于配置文件）

```bash
# Process a single table image
python demo_element.py --config ./config/Dolphin.yaml --input_path ./demo/element_imgs/table_1.jpeg --element_type table

# Process a single formula image
python demo_element.py --config ./config/Dolphin.yaml --input_path ./demo/element_imgs/line_formula.jpeg --element_type formula

# Process a single text paragraph image
python demo_element.py --config ./config/Dolphin.yaml --input_path ./demo/element_imgs/para_1.jpg --element_type text
```

```bash
# 处理单个表格图像
python demo_element.py --config ./config/Dolphin.yaml --input_path ./demo/element_imgs/table_1.jpeg --element_type table

# 处理单个公式图像
python demo_element.py --config ./config/Dolphin.yaml --input_path ./demo/element_imgs/line_formula.jpeg --element_type formula

# 处理单个文本段落图像
python demo_element.py --config ./config/Dolphin.yaml --input_path ./demo/element_imgs/para_1.jpg --element_type text
```

#### Using Hugging Face Framework | 使用Hugging Face框架

```bash
# Process a single table image
python demo_element_hf.py --model_path ./hf_model --input_path ./demo/element_imgs/table_1.jpeg --element_type table

# Process a single formula image
python demo_element_hf.py --model_path ./hf_model --input_path ./demo/element_imgs/line_formula.jpeg --element_type formula

# Process a single text paragraph image
python demo_element_hf.py --model_path ./hf_model --input_path ./demo/element_imgs/para_1.jpg --element_type text
```

```bash
# 处理单个表格图像
python demo_element_hf.py --model_path ./hf_model --input_path ./demo/element_imgs/table_1.jpeg --element_type table

# 处理单个公式图像
python demo_element_hf.py --model_path ./hf_model --input_path ./demo/element_imgs/line_formula.jpeg --element_type formula

# 处理单个文本段落图像
python demo_element_hf.py --model_path ./hf_model --input_path ./demo/element_imgs/para_1.jpg --element_type text
```

## 🌟 Key Features | 主要特性

- 🔄 Two-stage analyze-then-parse approach based on a single VLM
- 📊 Promising performance on document parsing tasks
- 🔍 Natural reading order element sequence generation
- 🧩 Heterogeneous anchor prompting for different document elements
- ⏱️ Efficient parallel parsing mechanism
- 🤗 Support for Hugging Face Transformers for easier integration

- 🔄 基于单一VLM的两阶段分析-解析方法
- 📊 在文档解析任务上的优异性能
- 🔍 自然阅读顺序元素序列生成
- 🧩 针对不同文档元素的异构锚点提示
- ⏱️ 高效的并行解析机制
- 🤗 支持Hugging Face Transformers，便于集成

## 📮 Notice | 通知
**Call for Bad Cases:** If you have encountered any cases where the model performs poorly, we would greatly appreciate it if you could share them in the issue. We are continuously working to optimize and improve the model.

**征集不良案例：** 如果您遇到模型表现不佳的案例，我们非常欢迎您在issue中分享。我们正在持续优化和改进模型。

## 💖 Acknowledgement | 致谢

We would like to acknowledge the following open-source projects that provided inspiration and reference for this work:
- [Donut](https://github.com/clovaai/donut/)
- [Nougat](https://github.com/facebookresearch/nougat)
- [GOT](https://github.com/Ucas-HaoranWei/GOT-OCR2.0)
- [MinerU](https://github.com/opendatalab/MinerU/tree/master)
- [Swin](https://github.com/microsoft/Swin-Transformer)
- [Hugging Face Transformers](https://github.com/huggingface/transformers)

我们要感谢以下开源项目为本工作提供的灵感和参考：
- [Donut](https://github.com/clovaai/donut/)
- [Nougat](https://github.com/facebookresearch/nougat)
- [GOT](https://github.com/Ucas-HaoranWei/GOT-OCR2.0)
- [MinerU](https://github.com/opendatalab/MinerU/tree/master)
- [Swin](https://github.com/microsoft/Swin-Transformer)
- [Hugging Face Transformers](https://github.com/huggingface/transformers)

## 📝 Citation | 引用

If you find this code useful for your research, please use the following BibTeX entry.

如果您在研究中发现此代码有用，请使用以下BibTeX条目。

```bibtex
@article{feng2025dolphin,
  title={Dolphin: Document Image Parsing via Heterogeneous Anchor Prompting},
  author={Feng, Hao and Wei, Shu and Fei, Xiang and Shi, Wei and Han, Yingdong and Liao, Lei and Lu, Jinghui and Wu, Binghong and Liu, Qi and Lin, Chunhui and others},
  journal={arXiv preprint arXiv:2505.14059},
  year={2025}
}
```

## Star History | 星标历史

[![Star History Chart](https://api.star-history.com/svg?repos=bytedance/Dolphin&type=Date)](https://www.star-history.com/#bytedance/Dolphin&Date)
