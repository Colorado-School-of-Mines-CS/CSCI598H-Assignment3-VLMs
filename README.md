# CSCI 598H Assignment 3: Fine-Tune a Vision-Language Model

## Goal

Take a small vision-language model, fine-tune it with LoRA on a small medical
VQA dataset, and show what changed. You write all of the code yourself, in
any structure you like.

- **Model:** [`Qwen/Qwen3-VL-2B-Instruct`](https://huggingface.co/Qwen/Qwen3-VL-2B-Instruct)
- **Dataset:** [`flaviagiammarino/vqa-rad`](https://huggingface.co/datasets/flaviagiammarino/vqa-rad):
  radiology images, each with a question and an answer. It has a `train`
  split (~1.8k examples) and a `test` split (~450 examples).
- **Method:** [LoRA](https://huggingface.co/docs/peft/main/en/developer_guides/lora)
  (parameter-efficient fine-tuning)

## What you need to do

1. **Before fine-tuning:** run the original model on the test set and measure
   its accuracy.
2. **Fine-tune:** train the model with LoRA on the training set.
3. **After fine-tuning:** run the fine-tuned model on the same test set and
   measure its accuracy again.
4. **Your own experiment:** change one thing and see what happens. You choose
   what to change, for example the LoRA rank, the learning rate, the number of
   training examples, which layers get LoRA, the prompt, or the image size.
5. **Explain your results** in `analysis.md`.

## A few rules

- Use the official `train` / `test` splits. Never train on the test set, and
  do not use it to choose hyperparameters.
- Use the same test set and the same scoring for every model, so the numbers
  are comparable.
- **Scoring.** Lowercase both the prediction and the answer, and remove their
  punctuation. Then report three accuracies:
  - **closed:** questions whose answer is *yes* or *no*;
  - **open:** all the other questions;
  - **overall:** all the questions together.

  You may also add a better metric of your own.

## What to submit

Push these to your private GitHub repository:

| Item | Description |
|---|---|
| Your code | Any structure. Add a short section to this README explaining how to run it. |
| `results.csv` | One row per experiment, with at least these columns: `experiment_id, description, n_train, n_test, trainable_params, train_time_min, overall_acc, closed_acc, open_acc` |
| `outputs/predictions/` | For each experiment, every test question with the ground-truth answer and the model's prediction |
| `outputs/figures/` | Training-loss curve(s), an accuracy comparison, and example images with their predictions |
| `analysis.md` | Your answers |

Do **not** commit model weights, LoRA adapters, datasets, caches, or access
tokens.

## Grading

| Component | Points |
|---|---:|
| Zero-shot evaluation | 15 |
| LoRA fine-tuning + evaluation | 30 |
| Your own experiment | 15 |
| Figures | 20 |
| `analysis.md` | 20 |
| **Total** | **100** |

## Helpful resources

- [Qwen3-VL model card (usage examples)](https://huggingface.co/Qwen/Qwen3-VL-2B-Instruct)
- [Chat templates for multimodal models](https://huggingface.co/docs/transformers/main/en/chat_templating_multimodal)
- [PEFT / LoRA documentation](https://huggingface.co/docs/peft/main/en/developer_guides/lora)
- [Hugging Face Datasets quickstart](https://huggingface.co/docs/datasets/quickstart)

This is an educational exercise. The fine-tuned model is not a clinical tool.

Follow the course policy on collaboration and AI tools.
