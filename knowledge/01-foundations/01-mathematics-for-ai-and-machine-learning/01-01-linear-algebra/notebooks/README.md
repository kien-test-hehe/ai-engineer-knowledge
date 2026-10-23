# Notebook registry · 1.1. Linear Algebra

## Notebook trong repo

| Notebook | Nội dung | Môi trường | Saved outputs |
|---|---|---|---|
| [01 · Tensor Shapes & Memory](./01-tensor-shapes-and-memory.ipynb) | ndim/shape/indexing, strides, permute, view/reshape, broadcasting, gradients | Python 3, PyTorch 2.x, CPU | Có, stdout của ví dụ xác định |
| [02 · Attention Shape Reasoning](./02-attention-shape-reasoning.ipynb) | MHA, attention scores, prefill/decode, silent bug, GQA grouping | Python 3, PyTorch 2.x, CPU | Có, stdout của ví dụ xác định |

Các notebook được viết theo cách khám phá từng cell; không chứa dataset/model weights hay kết quả GPU benchmark. Các phép toán minh họa cốt lõi đã được đối chiếu với PyTorch CPU. Nếu môi trường thay đổi, hãy chạy lại top-to-bottom để xác nhận và lưu outputs mới.

## Notebook ngoài repo

_Chưa đăng ký Colab/Kaggle/nbviewer bên ngoài; không tạo link chưa được xác minh._

## Kiểm tra outputs và độ tin cậy

- Các saved text outputs phản ánh những phép tính minh họa và không phụ thuộc GPU.
- Đây là tài liệu hỗ trợ thực hành; **chưa phải L3 completion evidence**.
- Theo [AGENTS.md](../../../../../AGENTS.md), thay đổi knowledge được review qua branch và Pull Request trước khi merge.
