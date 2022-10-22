# Models

## Getting a model fro Huggingface
* direct file download 
```git lfs clone https://huggingface.co/sberbank-ai/ruT5-base```
* auto-downloaded when used
```
from transformers import AutoTokenizer, AutoModelForMaskedLM
  
tokenizer = AutoTokenizer.from_pretrained("bert-base-uncased")
model = AutoModelForMaskedLM.from_pretrained("bert-base-uncased")
```

## Noticeable models
* https://huggingface.co/runwayml/stable-diffusion-v1-5