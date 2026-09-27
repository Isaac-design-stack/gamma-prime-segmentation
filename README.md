# Segmentation-Derived Morphology for Materials Informatics in Ni-Based Superalloys

Version 2.0.0

This repository contains the data, trained model, analysis notebooks and result tables supporting the manuscript on acquisition-proxy effects, target/measurement dependencies, validation design and feature-group contributions in segmentation-driven γ′ materials informatics.

## Contents

- `notebooks/01_segmentation_training_evaluation.ipynb` — Mask R-CNN training/evaluation workflow.
- `notebooks/02_downstream_materials_informatics.ipynb` — proxy diagnostic, provisional group-disjoint nested CV, feature ablation and direct-count comparison.
- `data/segmentation/train.json` — 88 training images, 23,603 γ′ annotations.
- `data/segmentation/val.json` — 22 validation images, 6,702 γ′ annotations.
- `model/model_final.pth` — trained Detectron2 checkpoint.
- `data/morphology/` — segmentation-derived morphology for the 99 matched records.
- `data/downstream/manuscript_analysis_dataset.csv` — composition, processing and recorded microstructural variables used in downstream analysis.
- `results/` — manuscript-supporting numerical outputs.
- `figures/` — final analysis figures available with this release.

## Dataset summary

The segmentation dataset contains 110 SEM images with 30,305 annotated γ′ instances. The fixed split contains 88 training images (23,603 instances) and 22 validation images (6,702 instances). Downstream analysis uses 99 records matched to composition, processing and morphology data.

## Main evaluation design

The downstream analysis evaluates five principal targets using provisional group-disjoint nested cross-validation. Groups are defined by exact equality across recorded composition and processing fields. This grouping is a conservative analytical device and does not establish physical specimen identity. Controlled ablations compare composition/processing features, segmentation-derived morphology and their combination.

Recorded γ′ size was measured using Fiji but numerically matches image scale in 96 of 99 records. It is therefore excluded from the principal downstream prediction targets and retained only for an acquisition-proxy diagnostic.

## Reproducibility

The archived COCO split files and trained checkpoint correspond to the segmentation workflow used for the manuscript. Raw SEM images are not included in this package unless redistribution permission is established separately. To rerun image-level training or inference, place the corresponding SEM files in a local image directory and update the path variables in the segmentation notebook.

The downstream notebook is repository-relative and can be run from the `notebooks` directory after installing the dependencies.

## Citation

Please cite the associated manuscript and the archived Zenodo release. Update the DOI in `CITATION.cff` after publishing the new Zenodo version.
