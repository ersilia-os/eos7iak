# Antimicrobial activity prediction against Campylobacter spp. from public ChEMBL data

Bioactivity prediction of growth inhibition in Campylobacter spp., trained as a binary (active/inactive) classifier from publicly available data in ChEMBL. The model is trained on a dose-response (MIC) assay. The output is a single ranking score; no consensus is computed because only one model is available.

This model was incorporated on 2026-05-19.


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
- **Output Dimension:** `1`
- **Output Consistency:** `Fixed`
- **Interpretation:** Probability of antimicrobial activity against Campylobacter spp. from a single ChEMBL-trained sub-model (MIC, dose-response).

Below are the **Output Columns** of the model:
| Name | Type | Direction | Description |
|------|------|-----------|-------------|
| general_mic_decoys | float | high | Probability from sub-model trained on MIC measurements aggregated across 251 ChEMBL assays (cutoff 10 uM; n=540 incl. decoys). Recommended threshold: 0.826. |


### Source and Deployment
- **Source:** `Local`
- **Source Type:** `Internal`
- **S3 Storage**: [https://ersilia-models-zipped.s3.eu-central-1.amazonaws.com/eos7iak.zip](https://ersilia-models-zipped.s3.eu-central-1.amazonaws.com/eos7iak.zip)

### Resource Consumption
- **Model Size (Mb):** `7`
- **Environment Size (Mb):** `1888`


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
