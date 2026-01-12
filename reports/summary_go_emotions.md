# Task 1A — Fine-tuning BERT for GoEmotions (Multi-label)

Generated: 2026-01-09 08:34:33

## Setup
- Dataset: google-research-datasets/go_emotions (raw)
- Model: bert-base-uncased
- Max length: 128
- Epochs: 3
- Learning rate: 2e-05
- Train batch size: 16
- Eval batch size: 32
- Weight decay: 0.01

## Data sizes used
- Train: 168980
- Validation: 21122
- Test: 21123

## Results
| Split | Loss | Micro-F1 | Macro-F1 | Micro-Precision | Micro-Recall |
|------|------|----------|----------|-----------------|--------------|
| Validation | 0.1105 | 0.3760 | 0.2867 | 0.5948 | 0.2749 |
| Test | 0.1109 | 0.3771 | 0.2846 | 0.5989 | 0.2752 |
