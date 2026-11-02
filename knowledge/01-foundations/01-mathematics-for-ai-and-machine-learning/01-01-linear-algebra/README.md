---
roadmap_id: "1.1"
roadmap_module: 1
content_status: partial
mastery: unassessed
target_minimum: L2
target_practical: L3
last_assessed: null
next_review: null
---
# 1.1. Linear Algebra

## Phạm vi syllabus gốc

- Scalars, vectors, matrices, tensors.
- Matrix multiplication, transpose, inverse, determinant.
- Vector spaces, basis, rank, linear independence.
- Dot product, inner product, outer product.
- Norms: L1, L2, Frobenius, spectral norm.
- Orthogonality và orthonormal vectors.
- Eigenvalues, eigenvectors, eigendecomposition.
- Singular Value Decomposition (SVD).
- Positive definite, positive semidefinite matrices.
- Projection, least squares, pseudoinverse.
- Matrix calculus và tensor shapes.
- Ứng dụng: embeddings, PCA, LoRA, attention, low-rank approximation.

## Kiến thức đã duyệt / đang review

- **Tensor Fundamentals for LLM**: [bản kiến thức L2 để review](notes/01-tensor-fundamentals-for-llm.md). Nội dung có evidence PASS; nội dung tệp và Pull Request vẫn chờ người học review/merge.
- Phạm vi: scalar/vector/matrix/tensor, shapes, indexing, dot/outer, matmul, Linear, broadcasting, layouts/strides, autograd cơ bản, MHA/KV cache/GQA shape reasoning.
- **Không đánh dấu cả module 1.1 đã hoàn thành**: inverse, determinant, eigen/SVD, rank, vector spaces và các chủ đề khác chưa được kiểm tra đầy đủ.

## L2 · Giải thích / Active recall

- **2026-10-21 · Tensor Fundamentals (phạm vi con)**: 54/60 = **90/100**, PASS theo ngưỡng ≥75/100, 12 câu vòng 4. [Evidence trong assessments.jsonl](../../../../progress/assessments.jsonl).
- Điểm 4 nhóm, mỗi nhóm quy đổi /25: Foundations 23.33; Shape & Operations 23.33; Memory & Autograd 20.00; LLM Applications 23.33.
- Phần còn củng cố: softmax key-vs-head axis, requires_grad khi freeze, trực giác alias/copy, grouped KV mapping.
- Thuộc tính YAML `mastery: unassessed` ở trên **áp dụng cho toàn module**, không phủ nhận việc phạm vi con Tensor Fundamentals đã PASS L2.

## L3 · Thực hành / Debug / Trade-offs

_Chưa được kiểm chứng theo chuẩn L3 độc lập._ Hai notebook bên dưới cung cấp ví dụ CPU và câu hỏi thực hành; không phải kết quả benchmarking GPU hoặc chứng nhận hoàn tất L3.

## Notebook và outputs

[Notebook registry](notebooks/README.md) · [Tensor shapes & memory](notebooks/01-tensor-shapes-and-memory.ipynb) · [Attention shape reasoning](notebooks/02-attention-shape-reasoning.ipynb).

## Tài liệu tham khảo, phiên bản

- Nội dung/bằng chứng: [Tensor Fundamentals for LLM](notes/01-tensor-fundamentals-for-llm.md).
- Python 3 + PyTorch 2.x; ví dụ nhỏ chạy CPU. Xem links đến tài liệu PyTorch chính thức trong note.

## Career Guide V2 cross-reference (not a mastery update)

**Active V2 Phase 1**: learn MatMul, Transpose, Dot/Inner Product and tensor shapes *through Q/K/V, attention scoring and masking* before expanding to distant linear-algebra proofs. Phase 2 later revisits math for gradients and backprop; Phase 9 revisits rank/SVD for LoRA and compression.

- [Full V2 learning path](../../../../curriculum/LEARNING_PATH_V2.md)
- [Math → LLM application map](../../../../curriculum/MATH_TO_LLM_MAP.md)
- [Current next exercises](../../../../progress/ACTIVE_PATH.md)
- [Foundation project (planned, not completed)](../../../../projects/00-attention-and-mini-transformer/README.md)

**Historical evidence remains unchanged:** Tensor Fundamentals L2 90% covers a sub-scope; the full module is still unassessed and L3 has not been certified.
