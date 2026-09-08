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

The large `.pth` files were not available to ChatGPT during package assembly. Before the Zenodo release, add `models/model_best_ap50.pth` and, if desired, `models/model_final.pth`. The best checkpoint is the important one for reproducing the reported evaluation.

## Running the work

See `REPRODUCIBILITY.md`. The original notebook retains its historical Google Drive paths because it is the exact research record. A second copy with outputs removed is included for easier review. Only path variables should be updated when adapting the notebook to the repository structure.

## Persistent archive

**Zenodo DOI:** `[INSERT DOI AFTER PUBLICATION]`  
**GitHub:** `[INSERT GITHUB REPOSITORY URL]`

After the first public Zenodo release, replace these placeholders and the corresponding placeholders in `CITATION.cff`, `.zenodo.json`, and `DATA_AVAILABILITY.md`.
