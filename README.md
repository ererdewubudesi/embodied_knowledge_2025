# Embodied Knowledge Understanding Benchmark

This repository provides the dataset for the paper:

> **Does Visual Grounding Enhance the Understanding of Embodied Knowledge in Large Language Models?**  
> *Zhihui Yang, Yupei Wang, Kaijie Mo, Zhe Zhao, Renfen Hu*
>
> > *EMNLP 2025 Findings (to appear)*

<!-- > Beijing Normal University · Tencent AI Lab   -->
<!-- > [[Paper PDF](./2996.pdf)] -->

<!-- ---

## 📘 Overview

Despite significant progress in multimodal language models (LMs), it remains unclear **whether visual grounding enhances their understanding of embodied knowledge compared to text-only models**.

To address this question, we propose a novel embodied knowledge understanding benchmark based on the perceptual theory from psychology, encompassing visual, auditory, tactile, gustatory, olfactory external senses, and interoception. The benchmark comprises two tasks, **SensoryVec** and **PerceptualQA**, which assess models’ understanding of embodied knowledge across different sensory modalities through vector comparison and question-answering tasks involving over 1,700 questions.

--- -->

## 🧩 Dataset Overview

### 1. **SensoryVec**

**Data**:

`SensoryVec/` contains:
- 349 adjective triples (target word – synonym – antonym)
- 1,047 contextualized sentences
- Model prediction results


**File Structure:**

```
SensoryVec/
└── SensoryVec_Dataset_with_Predictions.csv
```


### 2. **PerceptualQA**

**Data 1:**

`PerceptualQA/dataset/` contains:
- 1,400 multiple-choice questions

The dataset is divided into two parts:

- **`visual/`** — 200 questions for each visual subtask (**1,000 in total**)  
- **`non-visual/`** — 100 questions for each non-visual subtask (**400 in total**) 

Each dataset is available in both **English (`_en`)** and **Chinese (`_zh`)** versions.  
File names containing **`_answerA`**, **`_answer1`**, and **`_answer2`** indicate different answer configurations:
- **`_answerA`**: the correct answer is always option A  
- **`_answer1`**: answer positions determined by the **first random seed**  
- **`_answer2`**: answer positions determined by the **second random seed**

**File Structure:**

```
PerceptualQA/
└── dataset/
    ├── visual/
    │   ├── questions_with_answer1_en.json
    │   ├── questions_with_answer1_zh.json
    │   ├── questions_with_answer2_en.json
    │   ├── questions_with_answer2_zh.json
    │   ├── questions_with_answerA_en.json
    │   └── questions_with_answerA_zh.json
    └── non-visual/
        ├── questions400_with_answer1_en.json
        ├── questions400_with_answer1_zh.json
        ├── questions400_with_answer2_en.json
        ├── questions400_with_answer2_zh.json
        ├── questions400_with_answerA_en.json
        └── questions400_with_answerA_zh.json
```

**Data 2:**

`PerceptualQA/predictions/` contains:
- Model prediction results

Each subdirectory corresponds to a specific model (e.g., `Qwen2-7B`).  
Inside each model folder, JSON files store the predicted answers.  
All models provide predictions in English (`_en`), while some models additionally include Chinese (`_zh`) versions.  

In particular:
- `output1_en.json` and `output2_en.json`: predictions for the **visual subset** under two different random seeds  
- `output400_1_en.json` and `output400_2_en.json`: predictions for the **non-visual subset** under the same two random seeds  

These files include both the **selected option** and the **model rationale**, enabling detailed analysis of model behavior.

**File Structure:**
```
PerceptualQA/
└── predictions/
    ├── Mistral-7B-Instruct-v0.2/
    │   ├── output1_en.json
    │   ├── output2_en.json
    │   ├── output400_1_en.json
    │   └── output400_2_en.json
    ├── Qwen2-7B/
    │   ├── output1_en.json
    │   ├── output2_en.json
    │   ├── output400_1_en.json
    │   ├── output400_2_en.json
    │   ├── output1_zh.json
    │   ├── output2_zh.json
    │   ├── output400_1_zh.json
    │   └── output400_2_zh.json
    └── ...
```

**Data 3:**

`PerceptualQA/human_questions1400_with_answer1_sampled350/` contains:
- Human response data from seven native-speaking graduate students, with two independent responses per question
- Includes two files representing the complete human evaluation results:
  - `combined1.json`
  - `combined2.json`
- Each file contains 350 sampled questions (25% of the full dataset), proportionally covering all nine subtasks

**File Structure:**

```
PerceptualQA/
└── human_questions1400_with_answer1_sampled350
    ├── combined1.json
    └── combined2.json
```


<!-- ## 💡 Citation

If you use this benchmark in your research, please cite:

```bibtex
@article{yang2025embodied,
  title={Does Visual Grounding Enhance the Understanding of Embodied Knowledge in Large Language Models?},
  author={Yang, Zhihui and Wang, Yupei and Mo, Kaijie and Zhao, Zhe and Hu, Renfen},
  journal={Proceedings of the 2025 Annual Conference of the Association for Computational Linguistics},
  year={2025}
}
``` -->


## 📬 Contact

For questions or collaboration, please contact: yangzhihui@mail.bnu.edu.cn.

<!-- 
---

## 🧾 License

This dataset and benchmark are released for **academic and research use only**.  
Please refer to the paper for further details on ethical use and dataset construction. -->
