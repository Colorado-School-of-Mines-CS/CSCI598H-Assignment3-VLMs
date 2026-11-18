# Assignment 3 analysis

## 1. Setup

Describe your setup briefly: the prompt, the LoRA settings (rank, alpha,
target layers), the learning rate, the number of epochs, the batch size, the
precision, and the number of trainable parameters.

## 2. Results

| Experiment | What changed | Overall acc. (%) | Closed acc. (%) | Open acc. (%) | Train time (min) |
|---|---|---:|---:|---:|---:|
| Zero-shot | – | TBD | TBD | TBD | – |
| LoRA | – | TBD | TBD | TBD | TBD |
| Your experiment | TBD | TBD | TBD | TBD | TBD |

## 3. Figures

Insert your loss curve, your accuracy comparison, and at least 5 example
images (question, ground truth, prediction before fine-tuning, prediction
after fine-tuning).

## 4. Questions

1. How much did fine-tuning help? Did closed or open questions improve more, and why?
2. Look at your examples. Did the model learn better *visual understanding*,
   or mainly the *answer style* of the dataset? Give evidence.
3. What did you change in your own experiment, and what did you learn from it?
4. Which fraction of the parameters did you train? Why does LoRA fit on one
   GPU when full fine-tuning would not?
5. Where does your scoring fail? Show a reasonable answer that was marked wrong.
6. Name two reasons why this model should not be used for real medical decisions.
