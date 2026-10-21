# Tensor Fundamentals for LLM Engineers

> **Roadmap:** 1.1 Linear Algebra → Scalars, vectors, matrices, tensors, tensor shapes và ứng dụng attention.
>
> **Evidence:** 2026-10-21, vòng kiểm tra R4.1–R4.12, **54/60 = 90/100**, ngưỡng PASS ≥75/100.
> **Kết luận có giới hạn:** PASS bài **active recall / lý thuyết L2 cho phạm vi tài liệu này**. Chưa chứng nhận L3 thực hành và không đánh dấu toàn bộ module Linear Algebra đã đạt.
>
> Tài liệu ưu tiên bối cảnh **LLM, embeddings, Transformer, KV cache, inference**, không sử dụng computer vision.

## 1. Mô hình tư duy thống nhất

Một tensor trong PyTorch được mô tả thực dụng qua **values + shape + dtype + device + layout/strides**. Đây không phải định nghĩa hình học thuần túy của tensor.

| Đối tượng | Ví dụ shape | ndim | Trực giác |
|---|---|---:|---|
| Scalar | `()` | 0 | Một giá trị đơn lẻ |
| Vector | `(768,)` | 1 | 768 thành phần trong một trục |
| Matrix | `(10,768)` | 2 | 10 vector embeddings |
| Tensor nhiều trục | `(4,10,768)` | 3 | 4 câu × 10 tokens × 768 features |

**Bẫy khái niệm:** *vector trong không gian 768 chiều* nghĩa là vector có **768 thành phần**, nhưng tensor lưu vector ấy độc lập có **ndim = 1**. `ndim` là **số axes**, không phải số thành phần hay số samples.

- `shape`: kích thước của mỗi trục, ví dụ `(B,T,D)`.
- `ndim`: số trục, ví dụ 3.
- `numel`: tích kích thước các trục, ví dụ `B×T×D`.
- Thứ tự axes là **quy ước của model**. Một shape không tự cho biết trục nào là batch, token hay head.

Ví dụ `X.shape = (2, 6, 768)`:
- `X[1]` → `(6,768)` (một câu, axis Batch bị loại).
- `X[1:2]` → `(1,6,768)` (slice giữ axis Batch).
- `X[1,2]` → `(768,)` (embedding của token thứ ba trong câu thứ hai).
- `X.mean(dim=1)` → `(2,768)`, trung bình theo tokens cho từng feature; `keepdim=True` → `(2,1,768)`.

## 2. Đại số tuyến tính qua shape

Với vector `a∈R^m` và `b∈R^n`:

| Phép toán | Input | Output | Ý nghĩa |
|---|---|---|---|
| Hadamard `a*b` | cùng kích thước `(n,)` | `(n,)` | Nhân phần tử tương ứng |
| Dot `a@b` | hai vector `(n,)` | `()` | Tổng `Σ_i a_i b_i` |
| Outer `outer(a,b)` | `(m,)` và `(n,)` | `(m,n)` | Mọi tích `a_i b_j` |

Cosine similarity: `cos(a,b) = (a·b) / (‖a‖₂‖b‖₂)` cho hai vector khác 0. Nếu `b=2a` và `a≠0`, cosine = 1. Nó đo hướng tương đối, không phải luôn trực tiếp đo “cùng nghĩa”; embeddings của từ đối nghĩa vẫn có thể gần nhau do ngữ cảnh sử dụng.

Matrix multiplication: `(M,K) @ (K,N) → (M,N)`. Với batched matmul, các batch dimensions dẫn đầu được broadcast phù hợp; phép nhân diễn ra trên **hai chiều cuối**.

### nn.Linear giữ batch/token axes

`nn.Linear(128,256)` có weight `(256,128)` và bias `(256,)`. Một input `(B,T,128)` cho output `(B,T,256)`:

- Mỗi vector 128 features được chiếu sang 256 features bằng `y = x Wᵀ + b`.
- Hai axes `B`, `T` được giữ; cùng bộ tham số được dùng cho tất cả tokens.
- Không được nhầm **tăng feature dimension** với tăng số tokens.

## 3. Broadcasting, reduction và softmax

Broadcasting so khớp các axes **từ phải sang trái**. Hai kích thước tương thích nếu bằng nhau hoặc một bên bằng 1; axes bị thiếu được coi là kích thước 1 ở **bên trái**.

Ví dụ `X:(2,3,4)` và `b:(1,1,4)` → `Y=X+b:(2,3,4)`. Cùng một bias feature dùng tại 6 vị trí batch×token.

- `sum(dim=1)` hoặc `mean(dim=1)` mặc định loại trục đó.
- `keepdim=True` giữ trục đã reduce với kích thước 1.
- `softmax(dim=-1)` **giữ nguyên shape** và chuẩn hóa từng vector theo trục cuối.
- Attention scores `(B,H,Tq,Tk)` phải thường softmax theo `Tk` (key axis), không phải head axis. Khi có padding/causal mask, phân phối chỉ đặt trọng số lên những keys hợp lệ sau masking đúng cách.

## 4. Strides, storage, contiguous, views

Một tensor dense contiguous row-major có shape `(2,3,4)` thì strides `(12,4,1)`. Với storage_offset=0, địa chỉ tính theo **đơn vị phần tử**:

`offset(i,j,k) = 12i + 4j + k`.

Do đó `X[1,2,3]` có offset 23. Với view, công thức còn phải cộng `storage_offset` nếu khác 0.

`Y=X.permute(0,2,1)`:
- shape `(2,4,3)`, strides `(12,1,4)`;
- `Y[1,2,0] = X[1,0,2]`;
- thường **không** contiguous theo row-major mặc định;
- `permute` và `transpose` thường tạo view, **không copy** data.

**Phân biệt:**
- `permute`: thay đổi trật tự axes, ánh xạ index → storage thay đổi; không hoán đổi vật lý data.
- `reshape`: đổi cách nhóm phần tử theo **thứ tự logic**, có thể tạo view hoặc copy.
- `view`: chỉ hợp lệ khi strides/layout cho phép diễn giải shape mới **không cần copy**.
- `contiguous()`: nếu layout đã contiguous có thể không copy; nếu chưa, sẽ cấp phát và copy sang cách lưu contiguous.

**Một ví dụ silent bug trong attention:** từ `(B,T,H,Dh)` sang `(B,H,T,Dh)` phải đổi thứ tự axes bằng `permute(0,2,1,3)`. Chỉ `reshape` thành shape đích có thể tráo dữ liệu của token và head mặc dù tensor có shape hợp lệ.

Không suy luận contiguous chỉ từ quy tắc “stride giảm dần”; axes có size 1, memory formats và layouts khác cần xét riêng.

## 5. Expand, repeat, dtype và chi phí bộ nhớ

Tensor FP16 `b:(1,1,6)` chứa 6 phần tử = **12 bytes** dữ liệu thô.

- `b.expand(2,3,6)` có strides `(0,0,1)`: các positions logic chia sẻ cùng storage. Không tạo bản sao các giá trị; có metadata view.
- `b.repeat(2,3,1)` tạo tensor 36 phần tử mới = **72 bytes** được cấp phát thêm; nếu vẫn giữ `b` thì tổng storage dữ liệu của cả hai là **84 bytes**.
- Với cùng `numel`, FP32 chiếm 4 bytes/element, FP16 hoặc BF16 2 bytes/element, INT8 1 byte/element.
- Cẩn thận in-place trên expanded view: các vị trí logic có thể alias cùng dữ liệu gốc và các phép ghi chồng lấn thường bị từ chối.

Đừng cộng mù quáng `numel×element_size` của tất cả views để ước lượng VRAM; có shared storage, activations, gradients, optimizer states, temporaries, allocator overhead và KV cache.

## 6. Autograd và shared-parameter gradients

Một scalar loss không khiến tất cả gradients thành scalar. Với `W:(6,4)` và `b:(6,)` thì `W.grad:(6,4)`, `b.grad:(6,)` (nếu gradients được tính và tích lũy).

Ví dụ `X:(2,3,4)`, `b:(1,1,4)`, `Y=X+b`:
- Với `L=Y.sum()`, mỗi feature `b_k` được cộng ở 6 positions → `b.grad=[[[6,6,6,6]]]`.
- Với `L=Y.mean()`, có 24 output elements → mỗi `b_k` có gradient `6/24=0.25`.
- Nếu `L=L1+L2` và b dùng ở hai nhánh, gradients từ hai nhánh **cộng lại**, theo chain rule.
- `requires_grad=False` ngăn tính/tích lũy gradient cho parameter đó; nếu không có gradient cũ, `b.grad` là `None`. Nó không nhất thiết vô hiệu hóa gradients của tham số khác.

Các nhận định này liên quan đến các phép toán khả vi được nêu, giả sử `b` là leaf parameter và `backward()` được gọi đúng. Giá trị của gradient phụ thuộc hàm loss, không chỉ shape.

## 7. Multi-Head Attention, KV cache và GQA

Cho `X:(B,T,D)`, `H` heads và `Dh=D/H` (giả sử chia hết).

1. Q/K/V projections: thường từ `(B,T,D)`.
2. Reshape `(B,T,H,Dh)`, permute `(B,H,T,Dh)`.
3. `Kᵀ:(B,H,Dh,Tk)`, scores `Q@Kᵀ:(B,H,Tq,Tk)`.
4. `softmax(scores/√Dh, dim=-1)`; mask trước softmax nếu cần.
5. Attention weights @ V → context `(B,H,Tq,Dh)`.
6. Ghép heads → `(B,Tq,H·Dh)`, sau đó thường có output projection.

**Prefill vs decode:** Prefill tự chú ý toàn sequence có `Tq=Tk=T`, scores có `T²` phần tử mỗi head. Decode một token với KV cache có `Tq=1`, `Tk=cache_length`: scores kích thước `1×Tk`, chi phí hai attention matmuls cho **một step** tăng tuyến tính theo `Tk` (giữ B,H,Dh cố định). Không được đồng nhất số phần tử scores với actual memory allocation khi sử dụng fused/FlashAttention kernels.

**GQA:** ví dụ 8 query heads và 2 KV heads: mỗi KV head được chia sẻ bởi 4 Q heads. KV cache lưu 2 heads thay vì 8 → số phần tử K/V giảm **4 lần (75%)** ở cùng B,T,Dh,dtype. Không thể gọi thẳng `expand` từ head dimension size 2 thành 8; một cách logic là nhóm Q thành `(B,2,4,Tq,Dh)`, đưa singleton group axis vào K/V và broadcast hoặc dùng native GQA kernel. Nếu `repeat_interleave` thực sự materialize KV, memory advantage có thể mất ở tensor tạm.

### Khi làm bài LLM inference, luôn tự hỏi

1. Mỗi axis đang có **ý nghĩa gì**? Batch, Heads, Query tokens, Key tokens hay Features?
2. Phép toán tác động tới **hai chiều cuối**, hay chỉ đổi/gộp axes?
3. Có đang tạo **view hay copy**? Strides/output contiguous thế nào?
4. Softmax đang chuẩn hóa **trên trục nào**?
5. Gradient về **tham số gốc** gom từ bao nhiêu vị trí/nhánh?
6. Độ phức tạp tính theo `Tq` và `Tk`, hay đang nhầm prefill với decode?

## 8. Các lỗi từng mắc và đã sửa

| Hiểu nhầm trước đây | Tư duy đúng |
|---|---|
| Embedding 768D là tensor 768D | Vector có 768 components; tensor lưu độc lập có ndim=1 |
| `X[3]` vẫn có axis size 1 | Integer indexing bỏ axis; slice `X[3:4]` giữ axis |
| Matrix multiplication tùy ý shape | Inner dimensions phải khớp |
| `reshape` tương đương `permute` | Cùng shape nhưng có thể sai ngữ nghĩa token/head |
| `transpose` sửa RAM thành contiguous | Transpose thường chỉ thay strides |
| `view` là bản copy | View chia sẻ storage, không copy |
| `expand` lặp data thật | Singleton broadcast bằng zero strides |
| Loss scalar → gradients scalar | Gradient tensor theo parameter có cùng shape với parameter |
| Attention scores luôn vuông | Shape cuối là `(Tq,Tk)`; decode thường hình chữ nhật |
| GQA = expand trực tiếp KV axis 2 → 8 | Cần group mapping/broadcast hoặc native kernel |

## 9. Bài tự kiểm tra nhanh

Trước khi chạy code, suy luận:
1. `Q:(2,4,1,16)` và `K:(2,4,9,16)` → scores shape?
2. `X:(2,3,4)`, `b:(1,1,4)`, `L=(X+b).mean()` → `b.grad` mỗi phần tử?
3. `X.contiguous():(2,3,4)` strides (12,4,1); sau `permute(0,2,1)` shape/strides?
4. Vì sao GQA giảm KV cache size nhưng không cần lưu thêm KV cho mỗi query head?

Đáp án có thể đối chiếu trong notebook:
- [Tensor shapes & memory](../notebooks/01-tensor-shapes-and-memory.ipynb)
- [Attention shape reasoning](../notebooks/02-attention-shape-reasoning.ipynb)

## 10. Giới hạn và nguồn tham khảo

- Đây là tài liệu **active recall L2** đã được kiểm tra qua 12 câu vòng 4; **không** tuyên bố đã benchmark GPU hoặc hoàn thành bài thực hành L3.
- Các notebook là các **minh họa PyTorch chạy CPU**, không dựa trên model/dataset thực, không là đo đạc throughput hay VRAM production.
- PyTorch Tensor Views: https://docs.pytorch.org/docs/stable/tensor_view.html
- PyTorch Broadcasting Semantics: https://docs.pytorch.org/docs/stable/notes/broadcasting.html
- PyTorch nn.Linear: https://docs.pytorch.org/docs/stable/generated/torch.nn.Linear.html
- PyTorch Autograd: https://docs.pytorch.org/docs/stable/autograd.html
- PyTorch Scaled Dot-Product Attention: https://docs.pytorch.org/docs/stable/generated/torch.nn.functional.scaled_dot_product_attention.html

**Phạm vi module chưa đánh giá:** inverse/determinant, eigenvalues, SVD, basis, rank/linear independence, least-squares, pseudoinverse, low-rank approximation và nhiều nội dung syllabus 1.1 khác.
