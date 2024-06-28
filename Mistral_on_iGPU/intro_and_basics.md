# Exploring AI: Running Large Language Models on Laptop Using `IPEX-LLM` (Part 1: Introduction and GPU Basics)

<a href="https://drive.google.com/uc?export=view&id=1h5g6FSH9gg8d-XONsfwa1K1-eLhSxkp-" target="_blank">
  <img src="https://drive.google.com/uc?export=view&id=1h5g6FSH9gg8d-XONsfwa1K1-eLhSxkp-" width="100%" />
</a>

I've been using ChatGPT for a while and have tried other cloud-based LLM chat services. I'm curious if open-source local models can perform as well as subscribed services. This way, I wouldn't have to worry about sharing private secrets with chat services. 

I discovered a way to run large language models using a completely local setup. This means I use open-source models, no hosted APIs, and everything runs on my laptop without internet access.

 I am curious whether open-source local models can work as well as subscribed services. In the following blogs, I will:
> - Record stats from running various models
> - See how they perform
> - Share my experiences


This guide is for reflecting on what I've learned and helping those interested in local AI solutions.

## The Big Picture

I am trying to run LLMs on my laptop’s integrated GPU (iGPU) using the `IPEX-LLM` toolkit to speed up the processing.

### What is `IPEX-LLM`?

`IPEX-LLM` is a toolkit designed to optimize the performance of LLMs on Intel hardware, particularly focused on Intel CPUs and integrated GPUs (iGPUs). It ensures that the models are running efficiently on local devices.

### What is iGPU (Integrated Graphics Processing Unit)?

iGPUs are GPUs built into the same chip as the CPU, unlike dedicated GPUs, which are separate. iGPUs:

- Share memory with the CPU
- Are integrated into the main processor
- Are less powerful than discrete GPUs
- Are more power-efficient and cost-effective


While less powerful than discrete GPUs, they’re more power-efficient and cost-efficient. iGPUs are extremely common, and they are standard in most consumer laptops and many desktop computers.

### Running LLMs on iGPUs?

Traditionally, when we think about **GPUs** and **iGPUs**, we think about image and video rendering. However, GPUs have evolved to handle various computational tasks, particularly those that benefit from parallel processing, such as:

- **Machine Learning**
- **Simulations**


Thus, it would be much more powerful to run LLMs on iGPUs than CPUs, which are optimized for single-thread operations.

**Benefits of iGPUs:**

- Optimized for parallel processing tasks
- More powerful for running LLMs compared to CPUs

## Next Step

Next, I set my eyes on `Mistral 7B`, a highly optimized, open-source large language model designed for efficient natural language processing tasks. I will be running two versions of the `Mistral 7B` language model on an iGPU using `IPEX-LLM` and documenting my hands-on experience.

Stay tuned for Part 2, where I will present the initial results and analysis for running these models on a local setup, including performance metrics and practical insights.
