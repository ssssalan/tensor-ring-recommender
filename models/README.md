# Models

This directory will contain cleaned, reusable model implementations after the research code is separated from experiment-specific scripts.

Planned public components include:

- Tensor Ring core modules;
- Tensor Ring reconstruction utilities;
- recommendation / tensor-completion model wrappers;
- parameter-count utilities;
- shape and rank validation.

## Public-release rule

Do not move a research file here until it has been checked for:

- absolute local paths;
- private dataset identifiers;
- checkpoint paths;
- hard-coded machine-specific configuration;
- duplicate / obsolete experiment branches;
- unpublished method details that are not intended for release.

The final model API should keep tensor dimensions, TR ranks, dtype, and device configurable.
