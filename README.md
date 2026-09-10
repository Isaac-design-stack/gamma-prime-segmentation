# γ′ Instance Segmentation in Ni-Based Superalloy Microstructures

This is the public-release package for the one-class γ′ (`gamma_prime`) instance-segmentation workflow based on Detectron2 Mask R-CNN.

## Archived experiment

The files in this release were assembled from the completed experiment, not reconstructed from manuscript values. Internal consistency checks on this package confirm:

- **110 source micrographs**
- **30,305 COCO γ′ instance annotations**
- **88 training images**
- **22 validation images**
- fixed split seed recorded in the notebook: **42**
- reported evaluation checkpoint: **`model_best_ap50.pth`**
- checkpoint-selection metric: **`segm/AP50`**
- selected deployment confidence threshold: **0.40**

## Contents

```text
notebooks/       Exact executable notebook + lightweight output-stripped copy
data/images/     110 merged micrographs
data/annotations/Final COCO annotations and merge provenance logs
data/splits/     Exact train.json and val.json used in the experiment
models/          Location for large trained checkpoints
results/metrics/ COCO evaluation, threshold sweep, deployment metrics
results/figures/ Saved figures from the experiment
docs/            Deposit/reproduction documentation and checksums
```

## Model weights

The trained model checkpoints are distributed with the corresponding Zenodo
release because of their large file sizes and are not stored in the standard
GitHub repository history.

The archived checkpoints are:

- `model_best_ap50.pth` — best checkpoint selected using segmentation AP50 and
  used for the reported evaluation.
- `model_final.pth` — final training checkpoint.

For reproducing the reported evaluation results, `model_best_ap50.pth` is the
recommended checkpoint.

## Running the work

See `REPRODUCIBILITY.md`. The original notebook retains its historical Google Drive paths because it is the exact research record. A second copy with outputs removed is included for easier review. Only path variables should be updated when adapting the notebook to the repository structure.

## Persistent archive

GitHub repository: https://github.com/Isaac-design-stack/gamma-prime-segmentation

Zenodo DOI: https://doi.org/10.5281/zenodo.22663353

The Zenodo record provides the persistent archived release, including the
large trained-model checkpoints required for reproducibility.
