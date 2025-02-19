# Inference latency optimization

**Trying different methods for inference latency optimization & benchmark the performance**

This following results provides a comparison of inference results using different approaches on **an A100 40GB GPU**. 
The following configurations were tested:
- HF Transformer: This configuration serves as the baseline for performance comparison.
- KV Cache + Torch.Compile: This configuration applies KV cache and torch.compile optimizations to improve performance.
- VLLM: This configuration utilizes VLLM inference for enhanced performance.
- VLLM with Quantized Model: This configuration combines VLLM inference with a quantized model for further performance improvements.

**Tokens per sec**

<img width="592" alt="Screenshot 2025-02-18 at 10 48 33 PM" src="https://github.com/user-attachments/assets/bfed739e-292d-44e0-8f91-e6cf6ac080bf" />



**Response latency**

<img width="568" alt="Screenshot 2025-02-18 at 10 48 50 PM" src="https://github.com/user-attachments/assets/c0bbea28-204d-4948-b7df-32ff0b533207" />


The response tokens are limited to 200 tokens with low temperature 0.01 and top_p 0.01 values.
- kv cache and torch.compile provides significant response time improvements however needs warm up, it takes a long time during cache creation/recreation and loading
- vllm is almost 3x faster than baseline hf transformer
- quantized model with vllm performs better, however the improvement is not as big as expected (need to revisit)
