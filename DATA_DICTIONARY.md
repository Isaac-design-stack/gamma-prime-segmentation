# Data Dictionary

## `data/annotations/merged_gamma_prime_coco.json`
Final one-class COCO instance segmentation file. Category ID 1 is `gamma_prime`. It contains 110 image records and 30,305 annotations.

## `data/annotations/merge_report.csv`
Provenance table for the final merged images. Fields recorded by the workflow include `file_name`, `final_source`, image dimensions, annotation count, and whether an image originated in the older dataset.

## `data/annotations/replacement_log.csv`
Records cases where annotations from a later corrected CVAT export replaced an earlier source.

## `data/splits/train.json`, `val.json`
Exact COCO subsets used for training and validation: 88 and 22 images respectively.

## `results/metrics/coco_eval_results.json`
COCO bounding-box and segmentation metrics from the archived evaluation.

## `results/metrics/evaluation_summary.json`
Compact summary naming the evaluation checkpoint and headline segmentation AP metrics.

## `results/metrics/threshold_sweep.csv` / `threshold_sweep_best.json`
Confidence-threshold selection results. The archived best threshold is 0.40.

## `results/metrics/deployment_predictions_and_metrics.csv`
Per-image deployment output paths and derived morphology measurements. Units in pixels remain pixels unless a physical image calibration is explicitly supplied.
