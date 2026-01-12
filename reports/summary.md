# Task 1 — Fine-tuning BERT for Text Classification (AG News)

Generated: 2026-01-09 05:09:15

## Setup
- Dataset: sh0416/ag_news
- Model: bert-base-uncased
- Task: 4-class news topic classification (AG News)
- Max length: 128
- Epochs: 3
- Learning rate: 2e-05
- Train batch size: 16
- Eval batch size: 32
- Weight decay: 0.01
- Run mode: QUICK_RUN = False (full run if False)

## Data sizes used
- Train: 108000
- Validation: 12000
- Test: 7600

## Results
| Split | Loss | Accuracy | Macro-F1 |
|------|------|----------|----------|
| Validation | 0.1883 | 0.9485 | 0.9483 |
| Test | 0.1965 | 0.9455 | 0.9455 |

## Notes
- Labels were normalized to 0–3 (if needed) to match `num_labels=4`.
- Add: confusion matrix screenshot/table and a short error analysis section (example misclassifications).
