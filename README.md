# Trying different methods for inference latency optimization & benchmark the performance 

This following results provides a comparison of inference results using different approaches on an A100 40GB GPU. 
The following configurations were tested:
- HF Transformer: This configuration serves as the baseline for performance comparison.
- KV Cache + Torch.Compile: This configuration applies KV cache and torch.compile optimizations to improve performance.
- VLLM: This configuration utilizes VLLM inference for enhanced performance.
- VLLM with Quantized Model: This configuration combines VLLM inference with a quantized model for further performance improvements.


<img width="592" alt="Screenshot 2025-02-18 at 10 48 33 PM" src="https://github.com/user-attachments/assets/bfed739e-292d-44e0-8f91-e6cf6ac080bf" />


<img width="568" alt="Screenshot 2025-02-18 at 10 48 50 PM" src="https://github.com/user-attachments/assets/c0bbea28-204d-4948-b7df-32ff0b533207" />
