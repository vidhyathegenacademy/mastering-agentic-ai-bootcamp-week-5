# Mastering Agentic AI Bootcamp: Week 5

Week 5 project materials for an LLM DPO workflow that aligns a model to The Gen Academy's brand voice.

## Contents

- `notebooks/brand_voice_huggingface_dpo_demo.ipynb`: executed Hugging Face DPO notebook with charts and before/after comparison.
- `data/brand_voice_preferences.jsonl`: human-readable source preference dataset.
- `data/brand_voice_trl_dpo.jsonl`: TRL-compatible DPO dataset.
- `data/brand_voice_trl_dpo_train.jsonl`: train split.
- `data/brand_voice_trl_dpo_eval.jsonl`: held-out eval split.
- `data/gen_academy_brand_voice_dpo_train_120_raw.jsonl`: original 120-pair preference dataset.
- `requirements.txt`: Python dependencies for the notebook.

## Dataset

The dataset has 120 preference pairs across 12 brand-voice content categories.
The notebook uses 108 rows for training and 12 rows for held-out evaluation.

DPO training uses:

- `prompt`
- `chosen`
- `rejected`

The source dataset also includes `preference_reason`. That field is for humans reading the demo; it explains why the chosen response is better. It is not passed into DPO training.

## Run

```bash
pip install -r requirements.txt
jupyter notebook notebooks/brand_voice_huggingface_dpo_demo.ipynb
```

The notebook is already executed with local project results. To retrain from scratch, delete `outputs/gen-academy-brand-voice-hf-dpo` after running the notebook once locally.
