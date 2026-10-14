# Tensor Ring Model Overview

## Interaction tensor

A recommendation problem with temporal information can be represented as a sparse third-order tensor:

```text
X ∈ R^(I_user × I_item × I_time)
```

Only a small subset of entries is observed.

The learning task is to estimate observed and missing interactions using a compact low-rank representation.

## Tensor Ring representation

For an N-way tensor, Tensor Ring decomposition represents each mode using a three-dimensional core:

```text
G_k ∈ R^(R_k × I_k × R_(k+1))
```

with the cyclic condition:

```text
R_(N+1) = R_1
```

An entry is reconstructed through cyclic contraction of the selected core slices:

```text
X[i1, i2, ..., iN]
≈ trace(
    G1[:, i1, :] ·
    G2[:, i2, :] ·
    ... ·
    GN[:, iN, :]
  )
```

This avoids explicitly storing the full dense interaction tensor.

## Why it matters for recommendation

Tensor Ring models are attractive when:

- the interaction data contain more than two modes;
- the dense tensor is prohibitively large;
- low-rank structure can compress the representation;
- side information or contextual modes need to be incorporated;
- GPU-based batched contractions can be exploited.

## Current research questions

The project studies:

- how TR rank affects accuracy and parameter count;
- how side information affects sparse recommendation quality;
- how training cost scales with dataset size;
- how GPU kernels and memory layout affect runtime;
- how TR-based models compare with matrix-factorization and factorization-machine baselines.

## Scope of this document

This file describes the mathematical and systems motivation only.

Exact implementation details, training protocol, and final benchmark numbers should be taken from the released code and audited result files once they are added to this repository.
