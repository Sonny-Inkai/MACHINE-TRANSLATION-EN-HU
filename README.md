# Machine Translation Model Training and Performance Comparison

This repository contains code and results for training and evaluating a machine translation model using different frameworks and setups. The experiments compare the performance of training models using PyTorch and JAX/Flax frameworks, both on single and multiple devices.

## Table of Contents
1. [Introduction](#introduction)
2. [Setup](#setup)
3. [Experiments](#experiments)
   - [Experiment 1: PyTorch on Single GPU](#experiment-1-pytorch-on-single-gpu)
   - [Experiment 2: JAX/Flax on Single GPU](#experiment-2-jaxflax-on-single-gpu)
   - [Experiment 3: PyTorch on Multiple GPUs](#experiment-3-pytorch-on-multiple-gpus)
   - [Experiment 4: JAX/Flax on TPU](#experiment-4-jaxflax-on-tpu)
4. [Results](#results)
5. [Conclusion](#conclusion)
6. [Contact](#contact)

## Introduction
This project aims to evaluate the performance of machine translation models trained using different frameworks and hardware configurations. The model used is the MarianMTModel with the Helsinki-NLP/opus-mt-en-hu checkpoint. 

## Setup
### Common Settings
- **Pretrained Model:** MarianMTModel
- **Pretrained Tokenizer:** MarianMTModel
- **Model Checkpoint:** Helsinki-NLP/opus-mt-en-hu
- **Number of Model Parameters:** 76,149,760
- **Batch Size per Machine:** 64
- **Learning Rate:** 1e-5
- **Epochs:** 10
- **Tracking Metrics Tool:** Wandb

## Experiments
### Experiment 1: PyTorch on Single GPU
- **Notebook:** `test1-pytorch-single-machine`
- **Device:** GPU T4
- **Task:** Machine Translation
- **Framework:** PyTorch

#### Results
- **Training Loss:** 0.7915
- **Validation Loss:** 0.7646
- **Test Loss:** 0.7576
- **BLEU Score:** 10.14
- **Total Time:** 8829.48 seconds

### Experiment 2: JAX/Flax on Single GPU
- **Notebook:** `test2-jax-single-machine`
- **Device:** GPU T4
- **Task:** Machine Translation
- **Framework:** JAX/Flax

#### Results
- **Total Time:** 5586.22 seconds
- **Speed-up Compared to PyTorch:** 36.73%

### Experiment 3: PyTorch on Multiple GPUs
- **Notebook:** `pytorch-multiple-machine`
- **Device:** GPU T4 x2
- **Task:** Machine Translation
- **Framework:** PyTorch

#### Results
- **Total Time:** 5034.03 seconds
- **Speed-up Compared to JAX/Flax Single GPU:** 9.88%

### Experiment 4: JAX/Flax on TPU
- **Notebook:** `test3-jax-multiple-machine`
- **Device:** TPU-v3
- **Task:** Machine Translation
- **Framework:** JAX/Flax

#### Results
- **Total Time:** 372 seconds
- **Significant Speed-up Compared to All Previous Tests**

## Results
The results indicate that training with JAX/Flax on a TPU provides the fastest training time, significantly outperforming PyTorch on both single and multiple GPU setups.

## Conclusion
This series of experiments demonstrates the advantages of using JAX/Flax on TPU for machine translation tasks, achieving significant speed-ups in training times. The results also highlight the efficiency gains from using multiple GPUs in PyTorch.

## Contact
For any inquiries or further information, please contact:

- **Name:** Nguyễn Ngô Thành Đạt (Sonny)
- **Email:** sonnyinkai@gmail.com
- **Phone:** +84 868 781 774

---

© 2024 Sonny. All rights reserved.
