# Fine-tuning Qwen2.5-0.5B with LoRA

A quick experiment in fine-tuning a small language model, [Qwen2.5-0.5B-Instruct](https://huggingface.co/Qwen/Qwen2.5-0.5B-Instruct), to tell whether a movie review is positive or negative.

## What it does

1. Takes 200 movie reviews (half positive, half negative) from the IMDB dataset.
2. Shows them to the model one at a time, along with the correct answer, so it learns the pattern.
3. Trains only a small part of the model (LoRA) instead of the whole thing, which keeps it fast and light.
4. Tries the result on a new review.

Example: `"That movie was interesting."` gives `positive`.
## Files

- `LLM_Finetune.ipynb`: the notebook with all the code.
- `qwen2.5-0.5b-lora/`: the trained LoRA weights.
- `imdb_reviews_dataset/`: the dataset (not committed). Get `IMDB Dataset.csv` from Kaggle ("IMDB Dataset of 50K Movie Reviews").

## Running it

```
pip install torch transformers peft pandas tqdm
```

Put the CSV in `imdb_reviews_dataset/` and run the notebook. The CSV path in the notebook is hardcoded, so change it to match your machine.
