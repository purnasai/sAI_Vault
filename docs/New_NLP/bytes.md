```python
from llmlingua import PromptCompressor

llm_lingua = PromptCompressor("microsoft/phi-2")
prompt = "The Document I provided is a Tax Invoice. It has CHA services Table in the First page. It has Description, Rate, unit, Amount and other columns. It also has 9 Rows. Some services in table are Survey charges for container, lift of charges, Container detention charges and more. Can you retrieve that."
compressed_prompt = llm_lingua.compress_prompt(prompt, instruction="", question="", target_token=20)
```

Prompt compressor would work better when the prompt lenth is more than 2K tokens, I guess.
But it didn't work when the token are already minimum.

Check the compressed prompt
```python
{'compressed_prompt': 'The Document I provided is a Tax Invoice. It has CHA services Table in the First page. It has Description, Rate, unit, Amount and other columns. It also has 9 Rows. Some services in table are Survey charges for container, lift of charges, Container detention charges and more. Can you retrieve that.',
 'origin_tokens': 65,
 'compressed_tokens': 65,
 'ratio': '1.0x',
 'saving': ', Saving $0.0 in GPT-4.'}
```