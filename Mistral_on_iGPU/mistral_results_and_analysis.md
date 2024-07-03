# Exploring AI: Running Large Language Models on Laptop Using IPEX-LLM (Part 2: Initial Results and Analysis)


<a href="https://drive.google.com/uc?export=view&id=1UDbo0dJaHn6S6b7kx_l-Cx6LSQE9CorX" target="_blank">
  <img src="https://drive.google.com/uc?export=view&id=1UDbo0dJaHn6S6b7kx_l-Cx6LSQE9CorX" width="100%" />
</a>


In the previous part of this series, we discussed the basics of running large language models (LLMs) on GPUs and iGPUs, specifically using the Intel Extension for PyTorch (IPEX). Now, we move on to the practical aspects and my initial results running these models locally.



## My Journey with Mistral 7B on an iGPU

I tested the capabilities of IPEX-LLM by running two instruct versions of Mistral 7B, Q4_0 and Q4_K_M (both with 4-bit quantization, with K_M being more accurate), on an Intel Core Ultra 9 185GH machine equipped with an iGPU. The process was surprisingly smooth, thanks to the clear instructions provided on the IPEX-LLM website. While I encountered minor roadblocks, like navigating the HuggingFace website to find the correct model versions, the overall setup was straightforward.

### Optimizing for Efficiency: Success with iGPU

Despite running on iGPU, the response time was quicker than the language models operating on cloud servers that I have tried. I recorded the average ms/token, and the results were impressive:

**ms/token (milliseconds per token)**: Simply put, lower ms/token values indicate faster model performance. For example, if one model processes tokens at 10 ms/token, it will generate 100 tokens per second, while another model with 5 ms/token would only generate half as much.


<table width="100%">
  <tr>
    <td align="center" width="50%">
      <a href="https://drive.google.com/uc?export=view&id=1riPRwl3iw6d8JqG6R-SennyutZVWm7wO" target="_blank">
        <img src="https://drive.google.com/uc?export=view&id=1riPRwl3iw6d8JqG6R-SennyutZVWm7wO" width="95%" />
      </a>
      <br />
      <strong>Mistral Q4_0</strong>: Achieved 62 ms/token
    </td>
    <td align="center" width="50%">
      <a href="https://drive.google.com/uc?export=view&id=1riPRwl3iw6d8JqG6R-SennyutZVWm7wO" target="_blank">
        <img src="https://drive.google.com/uc?export=view&id=1riPRwl3iw6d8JqG6R-SennyutZVWm7wO" width="95%" />
      </a>
      <br />
      <strong>Mistral Q4_K_M</strong>: Achieved 82 ms/token
    </td>
  </tr>
</table>


There was no significant difference in terms of performance for both models, as the average GPU utilization hovered around 95%, showcasing remarkable efficiency on the iGPU. This is significant compared to traditional reliance on powerful, dedicated GPUs or cloud resources.


<style>
  .outlined-table {
    width: 100%;
    border: 1px solid white;
    border-collapse: collapse;
  }
  .outlined-table td {
    border: 1px solid white;
    padding: 10px;
  }
</style>

<table class="outlined-table">
  <tr>
    <td align="center">
      <a href="https://drive.google.com/file/d/1LPK8qvRyT_v3xHq7NKsM1kuyMPv8YwAw/view?usp=sharing" target="_blank">
        <img src="https://drive.google.com/uc?export=view&id=1XmfhK_K2uyITt_eLfj2PdNHeRg-_UT4C" width="95%" />
      </a>
      <p align="center"><strong>GPU usage for Mistral Q4_0</strong></p>
    </td>
  </tr>
  <tr>
    <td align="center">
      <a href="https://drive.google.com/file/d/1XmfhK_K2uyITt_eLfj2PdNHeRg-_UT4C/view?usp=sharing" target="_blank">
        <img src="https://drive.google.com/uc?export=view&id=1LPK8qvRyT_v3xHq7NKsM1kuyMPv8YwAw" width="95%" />
      </a>
      <p align="center"><strong>GPU usage for Mistral Q4_K_M</strong></p>
    </td>
  </tr>
</table>


## Why Local AI with iGPUs Matters

The ability to run complex AI models on iGPUs holds tremendous potential. It democratizes AI by making powerful tools accessible to a wider range of users, including:

- **Educational institutions**: Equip students with the power of AI for learning and exploration, allowing hands-on experience without needing expensive hardware.
  
- **Small startups and businesses**: Access AI capabilities without large initial costs, minimizing the need for new purchases, and lowering operational costs. This opens up the ability to develop and test AI models locally before scaling up.

- **Hobbyists and individual developers**: Easier accessibility to AI tools, enabling innovation and experimentation in AI.



## Next Step

Stay tuned for the final part of this series, where I'll share my overall experience working with IPEX-LLM and provide helpful tips along the way.