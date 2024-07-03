# Exploring AI: Running Large Language Models on Laptop
<a href="https://drive.google.com/uc?export=view&id=1oVh-rTrgr0IG_dXSHl3XylzAMcIoEnH4" target="_blank">
  <img src="https://drive.google.com/uc?export=view&id=1oVh-rTrgr0IG_dXSHl3XylzAMcIoEnH4" width="100%" />
</a>


## Using IPEX-LLM (Part 3: Tips for Your Local AI Journey)

Welcome to the third part of my blog series on running large language models (LLMs) using a completely local setup with IPEX-LLM. In Part 1, we explored the basics of GPUs and iGPUs and their significance in running LLMs efficiently. In Part 2, I shared my hands-on experience with running Mistral 7B on an iGPU, including initial results and performance analysis. Building on the knowledge and insights from the previous parts, this blog will cover some of the roadblocks I faced and their solutions. I hope you will find this helpful in optimizing your local AI setup and overcoming common challenges.

### Here are some helpful pointers:

1. **Leverage IPEX-LLM Resources**: The [IPEX-LLM github page](https://github.com/intel-analytics/ipex-llm) offers valuable documentation and guidance. It would also be helpful to investigate their GitHub page.
2. **Be Ready for Optimization**: Optimizing models for your specific hardware might involve parameter adjustments.

### Ollama Serve:

If you need to pull the model from Ollama, please remember to open a separate terminal and do it there while `ollama serve` is active.

### Num Predict:

My issues occurred in the section [“Using Ollama Run GGUF models”](https://github.com/intel-analytics/ipex-llm/blob/main/docs/mddocs/Quickstart/ollama_quickstart.md#using-ollama-run-gguf-models) (not needed for Linux users), which is the last step of the entire process. It tells you to copy a chunk of code and create a `.txt` file, which will be used to import to Ollama.

```
FROM ./mistral-7b-instruct-v0.1.Q4_K_M.gguf
TEMPLATE [INST] {{ .Prompt }} [/INST]
PARAMETER num_predict 64
```

This is set to only generate/predict 64 tokens. Remember to change it to 2048 or 4096 if the responses you get are incomplete.

### Embrace Troubleshooting:

Unexpected hurdles are part of the process. If you run into some issues, please reread the documents carefully, you might’ve missed something important! Also, it’s quite useful to ask an AI to set up your own AI ;)

## The Future of Local AI

My experience running Mistral-7B-Instruct models on an iGPU with IPEX-LLM highlights the potential of local AI execution. As we progress, I plan to explore additional optimizations and potentially benchmark even more models. I hope to inspire others to explore the possibilities of local AI with IPEX-LLM.