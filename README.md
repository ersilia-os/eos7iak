# Antimicrobial activity prediction against Campylobacter spp. from public ChEMBL data

Bioactivity prediction of growth inhibition in Campylobacter spp., trained as a binary (active/inactive) classifier from publicly available data in ChEMBL. The model is trained on a dose-response (MIC) assay. The output is a single ranking score; no consensus is computed because only one model is available.

This model was incorporated on 2026-05-19.Last packaged on 2026-06-01.

## Information
### Identifiers
- **Ersilia Identifier:** `eos7iak`
- **Slug:** `antimicrobial-activity-campylobacter`

### Domain
- **Task:** `Annotation`
- **Subtask:** `Activity prediction`
- **Biomedical Area:** `Diarrheal diseases`
- **Target Organism:** `Campylobacter spp`
- **Tags:** `Gram-negative bacteria`, `Antimicrobial activity`, `ChEMBL`

### Input
- **Input:** `Compound`
- **Input Dimension:** `1`

### Output
- **Output Dimension:** `3`
- **Output Consistency:** `Fixed`
- **Interpretation:** Probability of antimicrobial activity against Campylobacter spp. from 2 ChEMBL-trained sub-models, plus a quality-weighted consensus score.

Below are the **Output Columns** of the model:
| Name | Type | Direction | Description |
|------|------|-----------|-------------|
| consensus_score | float | high | Tanh-transformed quality-weighted consensus probability across the 2 sub-models. Recommended threshold: 0.893. |
| general_dose_response_decoys | float | high | Probability from sub-model trained on dose-response measurements aggregated across 4 ChEMBL assays (n=660). Recommended threshold: 0.804. |
| general_mic_decoys | float | high | Probability from sub-model trained on MIC measurements aggregated across 251 ChEMBL assays (cutoff 10 uM; n=540 incl. decoys). Recommended threshold: 0.848. |


### Source and Deployment
- **Source:** `Local`
- **Source Type:** `Internal`
- **DockerHub**: [https://hub.docker.com/r/ersiliaos/eos7iak](https://hub.docker.com/r/ersiliaos/eos7iak)
- **Docker Architecture:** `AMD64`, `ARM64`
- **S3 Storage**: [https://ersilia-models-zipped.s3.eu-central-1.amazonaws.com/eos7iak.zip](https://ersilia-models-zipped.s3.eu-central-1.amazonaws.com/eos7iak.zip)

### Resource Consumption
- **Model Size (Mb):** `18`
- **Environment Size (Mb):** `1890`
- **Image Size (Mb):** `2046.91`

**Computational Performance (seconds):**
- 10 inputs: `43.47`
- 100 inputs: `30.21`
- 10000 inputs: `576.32`

### References
- **Source Code**: [https://github.com/ersilia-os/chembl-antimicrobial-models](https://github.com/ersilia-os/chembl-antimicrobial-models)
- **Publication**: [https://github.com/ersilia-os/chembl-antimicrobial-models](https://github.com/ersilia-os/chembl-antimicrobial-models)
- **Publication Type:** `Other`
- **Publication Year:** `2026`
- **Ersilia Contributor:** [arnaucoma24](https://github.com/arnaucoma24)

### License
This package is licensed under a [GPL-3.0](https://github.com/ersilia-os/ersilia/blob/master/LICENSE) license. The model contained within this package is licensed under a [GPL-3.0-or-later](LICENSE) license.

**Notice**: Ersilia grants access to models _as is_, directly from the original authors, please refer to the original code repository and/or publication if you use the model in your research.


## Use
To use this model locally, you need to have the [Ersilia CLI](https://github.com/ersilia-os/ersilia) installed.
The model can be **fetched** using the following command:
```bash
# fetch model from the Ersilia Model Hub
ersilia fetch eos7iak
```
Then, you can **serve**, **run** and **close** the model as follows:
```bash
# serve the model
ersilia serve eos7iak
# generate an example file
ersilia example -n 3 -f my_input.csv
# run the model
ersilia run -i my_input.csv -o my_output.csv
# close the model
ersilia close
```

## About Ersilia
The [Ersilia Open Source Initiative](https://ersilia.io) is a tech non-profit organization fueling sustainable research in the Global South.
Please [cite](https://github.com/ersilia-os/ersilia/blob/master/CITATION.cff) the Ersilia Model Hub if you've found this model to be useful. Always [let us know](https://github.com/ersilia-os/ersilia/issues) if you experience any issues while trying to run it.
If you want to contribute to our mission, consider [donating](https://www.ersilia.io/donate) to Ersilia!
