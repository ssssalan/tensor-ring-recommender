# Tensor Ring Recommender

PyTorch/CUDA research on **Tensor Ring (TR) decomposition** for large-scale recommendation systems and tensor completion.

This repository is a recruiter-facing, public portfolio version of my ongoing research on low-rank tensor models. It focuses on how Tensor Ring representations can model sparse user-item-time interactions while keeping the implementation modular, measurable, and GPU-friendly.

> **Status:** the repository structure and research documentation are public. Research code and benchmark artifacts are being curated before release so that private datasets, absolute paths, temporary experiments, and unpublished components are not exposed.

---

## Research Focus

The project studies recommendation data as a sparse higher-order tensor rather than only a user-item matrix.

Typical interaction tensor:

```text
User × Item × Time
```

Research topics include:

- Tensor Ring Decomposition
- Tensor Completion
- Low-rank Representation
- Recommendation Systems
- PyTorch
- CUDA / GPU Training
- Sparse Data Modeling
- Parameter Compression
- Reproducible Evaluation

---

## Why Tensor Ring?

A matrix-factorization recommender models:

```text
User × Item
```

while many real recommendation scenarios naturally contain additional modes such as time, context, category, or behavior type.

Tensor methods extend this representation:

```text
User × Item × Time × ...
```

Tensor Ring decomposition represents a high-order tensor using a cyclic sequence of low-rank cores, allowing the model to capture multi-way interactions without explicitly materializing the full dense tensor.

Conceptually:

```text
Sparse Interaction Tensor
          |
          v
   Tensor Ring Cores
 G1 -- G2 -- G3 -- ... -- GN
  \_____________________/
          cyclic
          |
          v
 Low-rank Reconstruction
          |
          v
 Recommendation / Completion
```

---

## Current Research Direction

My current work investigates Tensor Ring based recommendation models with emphasis on:

1. **Scalability** — training on large sparse recommendation datasets.
2. **Parameter efficiency** — reducing the number of trainable parameters through low-rank factorization.
3. **GPU execution** — implementing training and evaluation with PyTorch/CUDA.
4. **Side information** — studying how auxiliary user/item information can improve sparse tensor completion.
5. **Parallelization** — exploring execution strategies that reduce memory traffic and improve hardware utilization.

---

## Development Snapshot

One historical MovieLens-25M development run used a third-order interaction tensor:

```text
162,541 users × 59,047 items × 50 time bins
```

with approximately:

```text
14.18M trainable parameters
```

and GPU training through PyTorch/CUDA.

This is included only to illustrate the scale of the research workload. It is **not presented as a final benchmark**. Final recruiter-facing benchmark tables will be added only after the experiment protocol, dataset split, seeds, and evaluation procedure are frozen and audited.

---

## Planned Public Repository Structure

```text
tensor-ring-recommender/
├── README.md
├── requirements.txt
├── models/
│   └── README.md
├── training/
│   └── README.md
├── evaluation/
│   └── README.md
├── configs/
│   └── README.md
├── datasets/
│   └── README.md
├── results/
│   └── README.md
├── figures/
│   └── README.md
└── docs/
    └── MODEL_OVERVIEW.md
```

---

## Tech Stack

### Core

`Python` · `PyTorch` · `CUDA`

### Data & Evaluation

`NumPy` · `Pandas` · `RMSE` · Sparse Interaction Data

### Research

`Tensor Ring` · `Tensor Decomposition` · `Tensor Completion` · `Recommendation Systems`

---

## Datasets

The research workflow has used large recommendation datasets including MovieLens and Amazon-derived interaction data.

Dataset files are **not committed** to this repository.

See [datasets/README.md](datasets/README.md) for the public data policy and expected preprocessing interface.

---

## Evaluation Principles

Final public benchmark results should document:

- dataset and exact split;
- tensor dimensions;
- random seed;
- model rank / TR ranks;
- trainable parameter count;
- validation RMSE;
- final test RMSE;
- training time;
- GPU model;
- checkpoint-selection rule.

The test set should be evaluated only after model selection is complete.

See [evaluation/README.md](evaluation/README.md).

---

## Documentation

- [Model overview](docs/MODEL_OVERVIEW.md)
- [Model module policy](models/README.md)
- [Training protocol](training/README.md)
- [Evaluation protocol](evaluation/README.md)
- [Dataset policy](datasets/README.md)
- [Results policy](results/README.md)

---

## Related Project

For my C++/OpenMP work on parallel matrix factorization and SGD, see:

[**Parallel SGD for Matrix Factorization**](https://github.com/ssssalan/parallel-sgd-matrix-factorization)

That project includes my first-author IEEE work on A-ASGD and complements this repository's PyTorch/CUDA tensor-decomposition focus.

---

## Author

**Peixin Li**  
M.S. Student, Southwest University

Research interests:

- Recommendation Systems
- Tensor Decomposition
- Parallel Machine Learning
- Large-scale Optimization

---

## License

This public portfolio repository is released under the MIT License.

Research datasets, unpublished experiment artifacts, and any third-party materials remain subject to their original licenses and release constraints.
