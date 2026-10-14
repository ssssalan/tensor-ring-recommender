# Training

The public training entry point will be added after the current research scripts are consolidated.

The cleaned training interface should expose configuration for:

- dataset path;
- tensor dimensions;
- TR ranks;
- learning rate;
- batch size;
- number of epochs;
- random seed;
- device;
- checkpoint directory;
- early-stopping patience.

## Experimental discipline

Model selection should use the validation split only.

The test split should be evaluated once after the selected checkpoint is reloaded.

Training logs should record enough metadata to reproduce a run, including configuration, seed, parameter count, epoch time, and validation metric.
