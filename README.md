# LLM_usecase

Please refer to the code file for example of using LLMs in CHP.

Please leave any comments if you have any questions. 

## 1. First refer to **usecase.ipynb** for data processing

## 2. Finetuning

### Set up environment for finetuning
```
conda create -n autotrain python=3.10.16
conda activate autotrain
sh finetune_env.sh
```

### Start finetuning

```
cd finetune
# change configs in filled_sft.yml
sh run.sh
```

### 3. Merge the lora parameters with the backbone model, and that is your own model 
```
autotrain tools merge-llm-adapter --base-model-path /home/jupyter/20000360102458359xu/LingfeiQian/saved_models/Llama31_8B_Instruct --adapter-path /home/jupyter/20000360102458359xu/LingfeiQian/finetune/code/Llama318BInstructCONVFINQAtrain11e4/ --output-folder /home/jupyter/20000360102458359xu/LingfeiQian/merged_models/Llama31_8B_Instruct_merged
```

## 3. Inference

### Set up environment for inference
```
conda create -n inference python=3.11
```