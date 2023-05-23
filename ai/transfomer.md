# Transformer

## Transformer chat

## Prerequisites
```
pip install torch
pip install transformers
```

## Code

```python
import sys
from transformers import AutoTokenizer, GenerationConfig
from transformers import AutoModelForSeq2SeqLM

model_name = 'google/flan-t5-base'
tokenizer = AutoTokenizer.from_pretrained(model_name)
model = AutoModelForSeq2SeqLM.from_pretrained(model_name)

for line in sys.stdin:
    tokens = tokenizer(line, return_tensors="pt")
    config = GenerationConfig(max_new_tokens=200)
    outputs = model.generate(**tokens, generation_config=config)
    print(tokenizer.batch_decode(outputs, skip_special_tokens=True))
```
