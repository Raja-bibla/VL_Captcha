
<div align="center">

# VL-KAN

### Variable-Length Visual Sequence Recognition with Kolmogorov–Arnold Networks

**An experimental deep learning framework exploring adaptive visual
sequence representation, variable-length recognition and
alignment-aware learning on synthetic CAPTCHA datasets.**

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)
![Deep Learning](https://img.shields.io/badge/Deep_Learning-8B5CF6?style=for-the-badge)
![Computer Vision](https://img.shields.io/badge/Computer_Vision-0066FF?style=for-the-badge)
![Research](https://img.shields.io/badge/Research-Implementation-059669?style=for-the-badge)

**Multi-Scale Feature Learning · Kolmogorov–Arnold Networks ·
Sequence Modelling · Curriculum Learning**

</div>

---

## Abstract

Visual sequence recognition presents several fundamental challenges
in computer vision, particularly when the number of characters,
their spatial positions and their visual appearances are unknown.

VL-KAN is a research-oriented PyTorch implementation that explores
the integration of convolutional feature extraction,
Kolmogorov–Arnold Networks (KANs), attention mechanisms and
alignment-aware sequence learning.

The framework investigates variable-length character recognition
using procedurally generated synthetic images, with an emphasis on
architectural experimentation, controlled evaluation and
reproducibility.

The project provides a modular environment for studying how
different neural network components influence character recognition,
sequence alignment and computational efficiency.

---

## Research Motivation

Conventional fixed-length recognition architectures assume a
predetermined output sequence length.

This assumption introduces limitations when dealing with
variable-length visual sequences.

Key research challenges include:

- Unknown character sequence lengths.
- Irregular spacing between characters.
- Spatial distortions and overlapping visual features.
- Alignment between visual representations and textual labels.
- Generalization across different synthetic image distributions.
- Balancing recognition quality and model complexity.

VL-KAN investigates these challenges through a combination of
adaptive feature representation and sequence-aware learning.

---

## Architecture Overview

The framework combines several research components:

| Component | Research Purpose |
| :--- | :--- |
| ResNet-18 sequence backbone | Convolutional visual representation |
| Multi-scale feature pyramid | Features at different spatial scales |
| Kolmogorov–Arnold Networks | Learnable nonlinear transformations |
| Attention-augmented KAN | Context-aware feature representation |
| CTC objective | Alignment-free sequence learning |
| Auxiliary prediction heads | Multi-task representation learning |
| Curriculum learning | Progressive learning across task difficulty |

The architecture separates visual representation learning from
sequence-level prediction, enabling controlled experimentation
with different model components.

---

## Kolmogorov–Arnold Networks

Traditional multilayer perceptrons use learnable linear weights
combined with fixed nonlinear activation functions.

Kolmogorov–Arnold Networks investigate an alternative approach
in which learnable univariate functions are associated with
connections between network components.

The Kolmogorov–Arnold representation theorem motivates the
representation of multivariate continuous functions through
compositions and sums of univariate functions.

A conceptual representation is:

$$
f(x_1,\ldots,x_n)
=
\sum_{q=0}^{2n}
\Phi_q
\left(
\sum_{p=1}^{n}
\phi_{q,p}(x_p)
\right)
$$

In this framework, KAN-based transformations are explored as
an alternative mechanism for nonlinear feature representation
within a visual recognition architecture.

---

## Machine Learning Concepts

| Concept | Application in the Framework |
| :--- | :--- |
| Convolutional Neural Networks | Spatial feature extraction |
| Residual Learning | Deep visual representations |
| Multi-scale Learning | Representation across spatial resolutions |
| Attention | Contextual feature relationships |
| Sequence Modelling | Variable-length character sequences |
| Multi-task Learning | Joint optimization of related objectives |
| Curriculum Learning | Progressive task complexity |
| Data Augmentation | Generalization across synthetic variations |
| Ablation Studies | Evaluation of architectural contributions |

---

## Research Framework

The repository is organized into independent modules covering
data generation, model architectures, optimization objectives,
evaluation and experimental comparisons.

```text
VL_Captcha/
│
├── data/
├── datasets/
├── decode/
├── evaluation/
├── experiments/
├── losses/
├── models/
│   ├── backbone/
│   ├── kan/
│   └── heads/
├── training/
│
├── environment.yml
├── requirements.txt
├── train.py
├── infer.py
└── README.md
```

This modular organization makes the project useful for examining
individual components and comparing architectural alternatives.

---

## Experimental Methodology

A meaningful evaluation of visual sequence recognition requires
more than a single aggregate accuracy value.

The framework includes utilities for examining character-level
recognition, sequence-level correctness, length prediction and
computational performance.

### Evaluation Metrics

| Metric | Description |
| :--- | :--- |
| Character Accuracy (CAcc) | Character-level recognition quality |
| Sequence Accuracy (SAcc) | Exact-match sequence correctness |
| Length Accuracy (LAcc) | Correct prediction of sequence length |
| Character Error Rate (CER) | Normalized character edit distance |
| Latency | Time required for prediction |
| Throughput | Number of samples processed per unit time |

### Character Error Rate

Character Error Rate measures the difference between predicted
and reference character sequences using edit distance.

$$
CER = \frac{S+D+I}{N}
$$

Where:

- **S** represents character substitutions.
- **D** represents character deletions.
- **I** represents character insertions.
- **N** represents the total number of reference characters.

Character Accuracy is defined in the implementation as:

$$
CAcc = 1-CER
$$

### Sequence Accuracy

Sequence accuracy measures the proportion of predictions that
exactly match their corresponding reference sequences.

$$
SAcc =
\frac{\text{Exact Matches}}
{\text{Total Sequences}}
$$

Character-level and sequence-level metrics provide complementary
perspectives on recognition quality.

---

## Architectural Comparisons

The repository includes experimental infrastructure for studying
the contribution of different neural network architectures.

| Architecture | Research Focus |
| :--- | :--- |
| DeepCaptcha | Fixed-length convolutional baseline |
| VariableLengthDeepCaptcha | Variable-length sequence baseline |
| KAN-based variant | Nonlinear representation learning |
| VL-KAN | Combined architectural approach |

The purpose of architectural ablation is to determine whether
individual components contribute meaningfully to recognition
quality and computational efficiency.

A complete experimental report should include:

- Dataset generation configuration.
- Model parameter counts.
- Training and validation methodology.
- Independent evaluation metrics.
- Hardware configuration.
- Inference latency measurements.
- Experimental seeds and uncertainty estimates.

---

## Experimental Results

The implementation includes evaluation and ablation utilities.

Numerical performance claims should be accompanied by
corresponding experimental logs, dataset configurations and
reproducible evaluation evidence.

No independently reproduced benchmark results are claimed
in this documentation.

---

## Technology Stack

| Category | Technology |
| :--- | :--- |
| Programming Language | Python |
| Deep Learning Framework | PyTorch |
| Numerical Computing | NumPy |
| Image Processing | Pillow |
| Neural Architectures | ResNet, KAN, Attention |
| Sequence Learning | CTC |
| Experiment Monitoring | TensorBoard |
| Environment Management | pip, Conda |
| Version Control | Git |

---

## Reproducibility

Reproducibility is an important consideration in experimental
machine learning.

The original implementation documents support for:

- Deterministic procedural data generation.
- Seed-controlled experimentation.
- Separate training and validation data generation.
- Model checkpointing.
- Optimizer and scheduler state preservation.
- Experiment monitoring.
- Structural ablation studies.
- Dependency configuration files.

Experimental results should always be interpreted in the context
of the corresponding dataset, architecture and hardware settings.

---

## Responsible Research

This repository is intended for educational study of computer
vision, neural network architectures and visual sequence
recognition using synthetic or explicitly authorized datasets.

It is not intended for bypassing CAPTCHA protections,
automating access to protected services or circumventing
website security mechanisms.

Potential defensive research applications include understanding
the limitations of visual verification systems and investigating
more robust and accessible verification mechanisms.

---

## Research Limitations

- Synthetic data may not represent real-world distributions.
- Results depend on the experimental configuration.
- Architectural improvements require controlled comparisons.
- Recognition accuracy alone does not establish generalization.
- Computational performance depends on hardware and software.
- Independent reproduction is necessary to validate reported
  experimental claims.

---

## Research Directions

- Investigate the interpretability of KAN-based representations.
- Analyze feature representations across architectural variants.
- Study computational efficiency and parameter utilization.
- Examine uncertainty estimation in visual sequence recognition.
- Compare generalization across controlled synthetic distributions.
- Explore accessibility-oriented verification research.
- Improve experimental documentation and reproducibility.

---

## References

1. He et al., **Deep Residual Learning for Image Recognition**.

2. Liu et al., **KAN: Kolmogorov–Arnold Networks**.

3. Graves et al., **Connectionist Temporal Classification:
   Labelling Unsegmented Sequence Data with Recurrent Neural
   Networks**.

4. Bengio et al., **Curriculum Learning**.

---

## Acknowledgements and Attribution

This repository contains an imported reference implementation
of the VL-KAN research project.

Credit for the original architecture, implementation and
experimental work belongs to the original developers.

Original source and applicable licensing information should
be retained with the repository.

Redistribution is subject to the permissions of the original
copyright holders.

---

<div align="center">

**Exploring the intersection of Computer Vision,
Sequence Learning and Adaptive Neural Architectures.**

Deep Learning · Computer Vision · Machine Learning Research

</div>
