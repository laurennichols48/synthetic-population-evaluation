# Evaluating synthetic LLM populations

**Pierre Bouquet, Lauren Nichols, and Geshi Yeung · MIT 6.8610**

Can language models reproduce demographic structure without flattening within-group variation—and do improvements in demographic alignment transfer to behavioral predictions?

[Read the report](reports/synthetic-populations-report.pdf)

## My contribution

I worked on model training and evaluation. This is a collaborative research project; the report and notebook archive retain the team’s work and authorship.

## Research workflow

1. Prepare ACS/IPUMS demographic records and leave-one-feature-out reconstruction tasks.
2. Establish baseline model predictions.
3. Compare supervised fine-tuning with balanced and population-weighted training data.
4. Evaluate reconstruction performance, class-level behavior, calibration, and stereotype flattening.
5. Examine downstream behavioral validity and feature ablations.

The report studies Qwen2.5-14B-Instruct; the notebook archive also includes other experimental configurations. These should not be treated as interchangeable replications of the reported model. Better demographic reconstruction does not by itself demonstrate better aggregate behavioral prediction.

## Notebook guide

| Stage | Files |
| --- | --- |
| Data | `ml_data_wrangling.ipynb`, `stage3_dataset_builder.ipynb` |
| Baseline | `ml_baseline_inference.ipynb` |
| Training | `stage3_sequential_experiment_pipeline.ipynb`, `stage_3_final.ipynb` |
| Evaluation | `0_de_biasing_eval.ipynb` through `4_compare_base_vs_ft.ipynb`, plus `4_compare_balanced_vs_natural_FINAL.ipynb` |
| Extensions | `behavioral_spillover_colab.ipynb`, `feature_ablation_base_vs_ft_colab.ipynb` |

All notebooks are in `notebooks/`.

## Reproduction status

This repository is a research archive, not an end-to-end runnable release. The notebooks retain Colab mounts, experiment-specific Drive paths, checkpoint dependencies and package-install cells. Configure these for your environment and select the intended experiment before running. Some cells refer to other notebooks using the original Drive layout; those references have not been refactored. GPU training and evaluation have not been rerun during portfolio preparation.

Obtain authorized ACS/IPUMS and downstream evaluation data separately. The preprocessing notebook now reads a local extract using `ACS_DATA_PATH` (default `usa_00006.csv.gz`); the private Drive download link was removed. Raw records, checkpoints, notebook outputs and personal notebook metadata are excluded. The original report is unchanged. No blanket software license is added to this shared work.
