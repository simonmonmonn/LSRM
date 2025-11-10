# LSRM
official code of "Remodeling Semantic Relationships in Vision-Language Fine-tuning"(AAAI-26).

## Environment
```shell script
conda create -n lsrm python==3.10
conda activate lsrm
pip install -r requirements.txt
pip install -e .
```
## TODO 
- [x] Code of experiments on LLaMA.

## Preparation
- For ScienceQA, please refer to the [official repo](https://github.com/lupantech/ScienceQA).
- For the weights of LLaMA, please refer to the [official form](https://forms.gle/jk851eBVbX1m5TAv5)  or unofficial HuggingFace repo [LLaMA-7B](https://huggingface.co/nyanko7/LLaMA-7B/tree/main) and [LLaMA-13B](https://huggingface.co/TheBloke/llama-13b).

```bash
<your path>/
  |-- lsrm
  |-- scripts
  |-- train.py
  |-- eval.py
  ......
  |-- data/
      |-- problem.json
      |-- pid_splits.json
      |-- captions.json
      |-- images
          |-- train          # ScienceQA train image
          |-- val            # ScienceQA val image
          |-- test           # ScienceQA test image
      |-- weights
          |-- tokenizer.model
          |--7B
              |-- params.json
              |-- consolidated.00.pth
          |--13B
              |-- params.json
              |-- consolidated.00.pth
              |-- consolidated.01.pth
```

## Fine-Tuning & Inference
```shell script
# LLaMA-7B
bash scripts/finetuning_sqa_7b.sh
bash scripts/eval_sqa_7b.sh

# LLaMA-13B
bash scripts/finetuning_sqa_13b.sh
bash scripts/eval_sqa_13b.sh
```
Fine-tuning takes around 40 minutes for LLaMA-7B and 1 hour for LLaMA-13B on 8x A800 (80G).

<!-- [Checkpoints](https://huggingface.co/JieShibo/MemVP-LLaMA-scienceqa/tree/main) -->


## Acknowledgements

- [LaVIN](https://github.com/luogen1996/LaVIN)
- [LLaVA](https://github.com/haotian-liu/LLaVA)
- [VL-PET](https://github.com/henryhzy/vl-pet)
- [MemVP](https://github.com/JieShibo/MemVP)

## Citation

```

```
