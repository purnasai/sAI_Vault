[Chatbot Arena](https://huggingface.co/spaces/lmsys/chatbot-arena) is a benchmarking platform after [Open LLM Leaderboard](https://huggingface.co/spaces/HuggingFaceH4/open_llm_leaderboard). In chatbot Arena users rank models based on their responses to the users questions.

Like Andrej karpathy mentioned in his talk [here](), Training of LLMs involves 4 steps, which later became 3 Major Steps:

- **Pretraining** - To give model ability to Generate Next word. It Generally need Entire Internet data to understand the world(words and their relation with next word). Since Training from Scratch needs Gaint GPUs.
- **Supervised Fine Tuning(SFT)** - To give model a context (or) tuning it to Custom usecase. [TRL](https://huggingface.co/docs/trl/index) library is used for it. It include support for Deepspeed, PEFT(Parameter Efficient Finetuning) with QLORA(Quantized Low Rank Adapter), Multi-GPU processing and more. [UNSLOTH](https://github.com/unslothai/unsloth) as another Option.

    [Ultrachat 200k](https://huggingface.co/datasets/HuggingFaceH4/ultrachat_200k) is one of the Best datasets used for SFT. One of the Best 7B model i.e [Zephyr 7B](https://huggingface.co/HuggingFaceH4/zephyr-7b-beta) is trained on its parent dataset called Ultrachat. 


- **Human Preference training** - To make Chatbot from SFT friendly, safe and helpful with Human Preference, which is also called RLHF(Reinforcement Learning with Human Feedback). TRL package can be used here as well. We use a techinque called DPO(Direct Preference optimization). PPO is also one more method. [HH-RLHF](https://huggingface.co/datasets/Anthropic/hh-rlhf) is one such dataset to use here. Refer to Huggingface DPO documentation [here](https://huggingface.co/docs/trl/dpo_trainer).


**Alignment Handbook**: is one documented explanation of How huggingface trained Zephyr-7B model. link [here](https://github.com/huggingface/alignment-handbook)

**GPUS**:

- Runpod.io
- vast.ai

**Deployment**:

- **Serverless**: is that the Same GPU is provided/shared with Other users. These providers charge very minimal per token. Some providers below:
    - Together.ai
    - Anyscale
    - perplexity.ai
    
    Like mentioned in the OpenAI document [here](https://platform.openai.com/docs/guides/text-generation/chat-completions-api) as shown below:

    ```python
    from openai import OpenAI
    client = OpenAI()

    response = client.chat.completions.create(
    model="gpt-3.5-turbo",
    messages=[
        {"role": "system", "content": "You are a helpful assistant."},
        {"role": "user", "content": "Who won the world series in 2020?"},
        {"role": "assistant", "content": "The Los Angeles Dodgers won the World Series in 2020."},
        {"role": "user", "content": "Where was it played?"}
    ]
    )
    ```
    It is kind of Sending the *Https* request to the API.

- **Dedicated**: GPU is only allocated for you. Packages like 
    - TGI(from Huggingface), 
    - [HF Endpoints](https://huggingface.co/inference-endpoints) where you can host your private model or model from hugginface for minimal costs. 
    - VLLM is also an opensource provider with **Paged attention** mechanism.

#### References:
- Video [here](https://www.youtube.com/watch?v=Ma4clS-IdhA&ab_channel=NielsRogge)
