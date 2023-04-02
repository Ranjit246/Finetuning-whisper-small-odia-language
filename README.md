# Finetuning-whisper-small-odia-language

Fine tuned Model can be found here: [On huggingface](https://huggingface.co/Ranjit/Whisper_Small_Odia_CV_11.0_5k_steps/)

odel is a fine-tuned version of [Ranjit/Whisper_Small_Odia_10k_steps](https://huggingface.co/Ranjit/Whisper_Small_Odia_10k_steps) on the [mozilla-foundation/common_voice_11_0 or](https://huggingface.co/datasets/mozilla-foundation/common_voice_11_0) dataset.
It achieves the following results on the evaluation set:
- Loss: 0.4827
- Wer: 23.4979

### Training hyperparameters

The following hyperparameters were used during training:
- learning_rate: 1e-05
- train_batch_size: 32
- eval_batch_size: 32
- seed: 42
- optimizer: Adam with betas=(0.9,0.98) and epsilon=1e-06
- lr_scheduler_type: linear
- lr_scheduler_warmup_steps: 200
- training_steps: 5000
- mixed_precision_training: Native AMP

### Training results

| Training Loss | Epoch | Step | Validation Loss | Wer     |
|:-------------:|:-----:|:----:|:---------------:|:-------:|
| 0.0018        | 50.0  | 1000 | 0.3315          | 24.0903 |
| 0.0           | 100.0 | 2000 | 0.4098          | 23.7236 |
| 0.0           | 150.0 | 3000 | 0.4827          | 23.4979 |
| 0.0           | 200.0 | 4000 | 0.4914          | 23.8928 |
| 0.0           | 250.0 | 5000 | 0.4953          | 23.7800 |


### Framework versions

- Transformers 4.28.0.dev0
- Pytorch 2.0.0+cu117
- Datasets 2.10.1
- Tokenizers 0.13.2
