# Reproducibility

## 1. Exact archived inputs

Use the files already supplied in this release rather than regenerating a split:

- `data/images/` — 110 merged images
- `data/annotations/merged_gamma_prime_coco.json` — 30,305 instance annotations
- `data/splits/train.json` — 88 images
- `data/splits/val.json` — 22 images

`merge_report.csv` and `replacement_log.csv` preserve dataset-merging provenance.

## 2. Notebook

`notebooks/gamma_prime_segmentation_main_original.ipynb` is the exact executable notebook supplied for the release. It intentionally retains historical Google Colab/Drive paths. `gamma_prime_segmentation_main_clean.ipynb` contains the same scientific code with execution outputs removed.

For a local/repository run, update path variables so they resolve to the repository directories. Do not alter the archived COCO split files when reproducing the reported experiment.

## 3. Recorded model configuration

The notebook records Detectron2 Mask R-CNN using `COCO-InstanceSegmentation/mask_rcnn_R_101_FPN_3x.yaml`, one `gamma_prime` class, batch size 2, base LR 1e-4, 18,000 iterations in the recorded run, and validation checkpointing on `segm/AP50`. Training augmentations include horizontal/vertical flips, 0/90/180/270-degree rotations, brightness adjustment, and contrast adjustment.

## 4. Model weights

Add the real `models/model_best_ap50.pth` before depositing to Zenodo. `results/metrics/evaluation_summary.json` identifies this as the checkpoint used for the archived evaluation. `model_final.pth` is useful but secondary for exact reported inference.

## 5. Threshold and outputs

The archived threshold sweep selects confidence threshold 0.40. Re-run evaluation and deployment only after loading the best checkpoint and exact validation split. Compare regenerated outputs with `results/metrics/` and `results/figures/`.

## 6. Environment

The supplied notebook recorded PyTorch 2.11.0+cu128 and Detectron2 0.6 in its Colab run. CUDA/PyTorch/Detectron2 compatibility can vary, so `requirements.txt` is intentionally readable rather than pretending all transitive versions were captured exactly.
