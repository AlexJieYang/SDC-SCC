# SDC-SCC

Descriptive comparisons of disruptive and consolidating scientist impact, laureate identification, metric correlations, matched groups and career trajectories.

## Install

Use Python 3.11. From the repository root:

```bash
python -m venv .venv
# Activate .venv using the command for your operating system.
python -m pip install -r requirements.txt
cp config.example.json config.json
jupyter lab
```

## Configure and run

Set `data_dir`, `output_dir` and `seed` in `config.json`, then open a notebook and run its cells in order with a fresh kernel. Relative directories resolve against the configuration file location. The repository root is the Jupyter working directory.

`RESEARCH_CONFIG` selects a configuration file; `RESEARCH_DATA_DIR`, `RESEARCH_OUTPUT_DIR` and `RESEARCH_SEED` provide environment overrides. The default seed is 2026. Tables use CSV, single-CSV ZIP archives or Excel. File naming is defined in `project_utils.DATA_FILES`; `input_schema.json` specifies the table field contracts.

Figures render in Jupyter. Explicit file exports use the configured output directory. Notebooks are stored with clear execution state.

## Notebooks

- `fig 2 laureates.ipynb`
- `fig 3 correlation.ipynb`
- `fig 4 5 IR AR.ipynb`
- `fig 6 Dual impact and two types of scientists.ipynb`
- `fig 7 Control.ipynb`
- `fig 7 career.ipynb`

## Methods

IR divides the number of selected laureates by the number of laureates in the scientist table. Basic AR is mean zero-based laureate rank. Normalized AR divides this mean by the observed first-to-last laureate rank span. Control matching uses nearest values with replacement. Career error bars show standard deviations. Kendall correlation panels use the same twelve scientist metrics for each group.

Bootstrap intervals use full-size resamples of finite observations and deterministic random generators.

## Source checks

```bash
python scripts/validate_sources.py
```

This command parses Python and notebook source, validates JSON and checks notebook execution state. GitHub Actions runs the same source checks without executing research analyses.

## Citation and license

`CITATION.cff` provides software citation metadata. Cite the associated publication using its bibliographic record. Project code and documentation use the MIT license. Third-party data retain their providers' licenses and access terms.
