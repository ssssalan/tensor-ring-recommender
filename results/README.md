# Results

This directory will contain audited recruiter-facing result tables only.

## Development snapshot

A historical MovieLens-25M development run used:

| Field | Value |
|---|---:|
| Tensor dimensions | 162,541 × 59,047 × 50 |
| Trainable parameters | 14,184,832 |
| Framework | PyTorch |
| Accelerator | CUDA |

These values document research scale only and are **not a final benchmark**.

## Final benchmark policy

Final tables should be committed only after:

1. dataset split is frozen;
2. seeds are documented;
3. validation is used for checkpoint selection;
4. test is evaluated only after checkpoint reload;
5. parameter-count definitions are consistent across models;
6. hardware and runtime settings are recorded.

Recommended comparison columns:

```text
Model | Params | Best Val RMSE | Test RMSE | Train Time | GPU Memory
```
