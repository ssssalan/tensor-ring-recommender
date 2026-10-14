# Evaluation

The primary recommendation / tensor-completion metric used in the current research workflow is **RMSE**.

For a frozen test set:

```text
RMSE = sqrt(mean((prediction - target)^2))
```

## Required public benchmark fields

Every final benchmark row should document:

- model;
- dataset;
- tensor dimensions;
- train / validation / test split;
- seed;
- model ranks;
- trainable parameters;
- best validation RMSE;
- final test RMSE;
- training time;
- hardware;
- checkpoint-selection rule.

## Test-set policy

The test set should not be used for:

- early stopping;
- hyperparameter selection;
- model selection;
- epoch-by-epoch tuning.

The final test metric should be computed only after the best validation checkpoint is selected and reloaded.
