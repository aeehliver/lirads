# LiverAI: LI-RADS v2018 Categorization of Free-text MRI Reports

A domain-specific large language model for automated LI-RADS v2018 categorization from free-text MRI reports.

## Overview

LiverAI is a context-based chatbot built on GPT-4 architecture, developed to assist in the LI-RADS v2018 categorization of hepatic observations based on free-text radiological descriptions from MRI reports. This project was developed between November 2023 and January 2024, sponsored by the Spanish Society of Liver Diseases (AEEH).

## Performance Results

### Dataset Characteristics
- Total observations: 291
  - Training set: 141 observations (51 real + 90 synthetic)
  - Validation set: 30 observations
  - Test set: 120 observations
- Median lesion size: 15mm (IQR: 12-18mm)
- Focus on small liver observations (<20mm)

### Model Performance

#### Standalone Performance (vs Ground Truth)
- Overall LI-RADS categorization agreement: κ = 0.54 (95% CI: 0.42-0.65)
- Accuracy for LR-5 detection:
  - Sensitivity: 0.76 (95% CI: 0.69-0.86)
  - Specificity: 0.96 (95% CI: 0.91-1.00)
- Dichotomized malignancy approach:
  - Agreement: κ = 0.58 (95% CI: 0.42-0.73)
  - Sensitivity: 1.00 (95% CI: 1.00-1.00)
  - Specificity: 0.51 (95% CI: 0.37-0.66)

#### Combined Strategies Performance

1. Double Reading with Arbitration
- Agreement: κ = 0.87-0.88
- LR-5 Sensitivity: 0.98
- LR-5 Specificity: 0.92-0.98
- Workload reduction: 52.5-60%

2. Triage Strategy
- Agreement: κ = 0.86-0.87 (radiologists), κ = 0.76 (hepatologist)
- LR-5 Sensitivity: 0.85-1.00
- LR-5 Specificity: 0.92-0.96
- Workload reduction: 45%

## Implementation Details

### Model Architecture
- Base: GPT-4
- Training period: November 2023 - January 2024
- Input: Free-text MRI report descriptions
- Output: LI-RADS v2018 categorization

### Development Process
1. Data transformation of LI-RADS system into AI-optimized textual descriptions
2. Model fine-tuning and embeddings application
3. Prompt engineering optimization
4. Validation against publicly available generic chatbots

## Usage

The model can be integrated into clinical workflows in several ways:

1. Standalone assessment
2. Double reading with arbitration strategy
3. Triage tool for prioritizing cases

## License
Apache 2.0

## Citation

If you use this work in your research, please cite:

```bibtex
@article{matute2024utilizing,
  title={Utilizing a domain-specific large language model for LI-RADS v2018 categorization of free-text MRI reports: a feasibility study},
  author={Matute-González, Mario and others},
  journal={Insights into Imaging},
  year={2024},
  volume={15},
  pages={280},
  doi={10.1186/s13244-024-01850-1}
}
