# Datasets

Large datasets are intentionally excluded from this repository.

## Target data format

The public preprocessing interface will use indexed interaction records such as:

```text
user, item, time, value
```

where categorical identifiers are mapped to contiguous integer indices before training.

## Research datasets

The research workflow has used:

- MovieLens recommendation data;
- Amazon-derived interaction data.

Raw or processed datasets are not redistributed here.

## Reproducibility policy

A public experiment should document:

- source dataset;
- preprocessing steps;
- filtering rules;
- index mapping procedure;
- time discretization procedure;
- train / validation / test split;
- split seed or frozen split artifact.

Generated data directories and large binary tensors should remain ignored by Git.
