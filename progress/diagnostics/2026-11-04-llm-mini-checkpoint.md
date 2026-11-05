# LLM Fundamentals — mini checkpoint (2026-11-04)

**Status: targeted subscope PASS, 19.5/20.** Q/K/V projection and GQA 10/10; BF16 KV cache computation 9.5/10. Not full LLM L2, not L3.

- Inputs: X=[3,1024,1536], 24 Q heads, 6 KV heads, d_head=64, 24 layers, BF16.
- Correct WQ=[1536,1536], WK=WV=[1536,384]; Q=[3,24,1024,64], K/V=[3,6,1024,64]. Independent learned projections of current hidden states, KV heads shared across four Q heads.
- Correct cache bytes: 3*24*2*6*1024*64*2=113246208 bytes=108 MiB (~113.25 MB). Deduct 0.5 for calling it 108 MB rather than 108 MiB.
- Next: diagnostic Round 2 on training, SFT, LoRA/QLoRA, gradient flow and model evaluation.
- Preserve Round 1 score (63/100) and do not treat mini checkpoint as full module pass.
