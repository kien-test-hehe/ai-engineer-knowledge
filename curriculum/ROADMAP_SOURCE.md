# AI ENGINEER ROADMAP 2026

Full Competency Map • Cập nhật ngày 13/10/2026 • Từ Fundamentals đến Advanced Production AI

Đây là bản đồ kiến thức dành cho một Middle AI Engineer thực thụ, không chỉ biết sử dụng Hugging Face, gọi LLM API hoặc xây chatbot bằng LangChain, mà còn phải hiểu mô hình hoạt động thế nào, tối ưu ra sao, triển khai thế nào và xử lý sự cố trong production.

Tôi sẽ bao phủ cả Traditional Machine Learning, Deep Learning, Computer Vision, NLP, Generative AI, LLM Engineering, Agentic AI, Model Optimization, MLOps, Infrastructure và System Design.

Một điểm quan trọng: AI Engineer năm 2026 không phải một chức danh có bộ kiến thức cố định. Người chuyên xây AI Application sẽ cần đào sâu những thứ khác với người chuyên LLM Inference hoặc Computer Vision. Vì vậy, bản đồ này là toàn bộ phạm vi kiến thức để học và lựa chọn chuyên môn, chứ không phải yêu cầu mọi Middle Engineer đều phải thành thạo 100%.

## Tổng quan các khối kiến thức

Lộ trình từ căn bản đến chuyên sâu

LEVEL 1 • FOUNDATIONS

Math · Python · CS · SQL · Data · ML

LEVEL 2 • DEEP LEARNING

PyTorch · Neural Networks · CNN · Transformers · Training

LEVEL 3 • MODERN AI ENGINEERING

LLM · RAG · Agents · MCP · Fine-tuning · Multimodal

LEVEL 4 • PRODUCTION & OPTIMIZATION

Serving · Quantization · Evaluation · MLOps · Security · Cloud

LEVEL 5 • ADVANCED / SPECIALIZATION

Distributed AI · CUDA · RL · Research · Large-scale Architecture

### Cách xác định mức độ cần học

| Ký hiệu  | Kỳ vọng đối với Middle AI Engineer                                                |
| -------- | --------------------------------------------------------------------------------- |
| Core     | Phải hiểu và tự triển khai được, không phụ thuộc hoàn toàn vào tutorial           |
| Working  | Biết áp dụng, lựa chọn, debug và giải thích trade-off                             |
| Advanced | Hiểu cơ chế và có thể đi sâu theo hướng chuyên môn; không bắt buộc cho mọi vị trí |

# PHẦN I. FOUNDATIONS

## 1. Mathematics for AI & Machine Learning

Mức độ: Core • Nền tảng cho ML, DL, quantization và optimization

### 1.1. Linear Algebra

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

### 1.2. Calculus & Multivariable Calculus

- Derivatives, partial derivatives.
- Chain rule, product rule, quotient rule.
- Gradient, Jacobian, Hessian.
- Directional derivatives.
- Taylor series và Taylor approximation.
- Critical points, local/global optima.
- Gradient-based optimization.
- Backpropagation dưới góc nhìn chain rule.
- Automatic differentiation.
- Ứng dụng: tính gradient cho neural networks, phân tích loss landscape.

### 1.3. Probability Theory

- Random variables, probability distributions.
- Conditional probability, Bayes' theorem.
- Joint, marginal và conditional distributions.
- Expectation, variance, covariance.
- Correlation và independence.
- Gaussian, Bernoulli, Binomial, Poisson, Uniform distributions.
- Law of Large Numbers, Central Limit Theorem.
- Maximum Likelihood Estimation (MLE).
- Maximum A Posteriori (MAP).
- Entropy, cross-entropy, KL divergence, JS divergence.
- Sampling và Monte Carlo.
- Ứng dụng: probabilistic modeling, sampling tokens, Bayesian reasoning.

### 1.4. Statistics

- Descriptive statistics.
- Sampling bias, selection bias.
- Confidence intervals và hypothesis testing.
- P-value và effect size.
- Z-test, t-test, chi-square test.
- Bootstrapping.
- A/B testing, sample size và statistical power.
- Correlation vs causation.
- Outliers và robust statistics.
- Multiple comparisons và statistical significance.
- Ứng dụng: đánh giá model, xác định cải thiện có thực sự đáng kể.

### 1.5. Optimization Theory

- Convex và non-convex optimization.
- Gradient Descent và Stochastic Gradient Descent.
- Momentum, Nesterov.
- AdaGrad, RMSProp, Adam, AdamW.
- Learning rate schedules.
- Gradient clipping.
- L1/L2 regularization và weight decay.
- Saddle points và vanishing gradients.
- Constrained optimization.
- Lagrange multipliers.
- Numerical stability.
- Ứng dụng: training, fine-tuning và debugging convergence.

### 1.6. Numerical Computing

- Floating-point arithmetic.
- IEEE 754: sign, exponent, mantissa.
- FP64, FP32, TF32, FP16, BF16.
- FP8 E4M3, FP8 E5M2.
- INT8, INT4, FP4.
- Rounding, overflow, underflow.
- Numerical precision và error propagation.
- Stable softmax và log-sum-exp trick.
- Mixed-precision computation.
- Matrix multiplication, GEMM và accumulation precision.
- Ứng dụng: quantization, AMP, GPU inference.

## 2. Programming & Computer Science Fundamentals

Mức độ: Core

### 2.1. Python Engineering

- Python syntax, functions, classes, modules.
- Object-Oriented Programming.
- Functional programming basics.
- Decorators, generators, iterators.
- Context managers.
- Type hints, dataclasses, Pydantic.
- Exceptions và error handling.
- Virtual environments, `uv`, `pip`, `conda`.
- Packaging và dependency management.
- Asyncio, async/await.
- Multiprocessing, multithreading và GIL.
- Memory profiling và Python performance optimization.

### 2.2. Data Structures & Algorithms

- Arrays, lists, stacks, queues.
- Hash maps, sets.
- Linked lists.
- Trees, heaps, tries.
- Graphs.
- Sorting và searching.
- Binary search.
- BFS và DFS.
- Dynamic programming basics.
- Big-O time và space complexity.
- Trade-off giữa latency, CPU và memory.

### 2.3. Software Engineering

- SOLID principles.
- Separation of concerns.
- Design patterns.
- Modular architecture.
- Dependency injection.
- Configuration management.
- Logging và exception strategy.
- Code readability và maintainability.
- Refactoring và code review.
- API contracts và backward compatibility.

### 2.4. Testing & Quality Assurance

- Unit testing với pytest.
- Integration testing.
- End-to-end testing.
- Mocking external services.
- Property-based testing.
- Regression testing.
- Load testing.
- Contract testing.
- CI test automation.
- Test coverage và mutation testing (Advanced).

### 2.5. Git & Collaboration

- Git commits, branches, merges.
- Rebase, cherry-pick, revert.
- Pull requests.
- Merge conflict resolution.
- Semantic versioning.
- GitHub Actions hoặc GitLab CI.
- Conventional commits.
- Code ownership và review workflows.

### 2.6. Operating Systems & Linux

- Processes, threads.
- CPU scheduling.
- Virtual memory, paging.
- File systems và permissions.
- Linux CLI, shell scripting.
- Signals và process management.
- Environment variables.
- SSH và remote development.
- CPU, RAM, I/O monitoring.
- Containers vs virtual machines.
- Debugging process, memory leak, file descriptor exhaustion.

### 2.7. Networking Fundamentals

- TCP/IP, HTTP/HTTPS.
- DNS, TLS.
- REST và gRPC.
- HTTP/2, WebSocket, SSE.
- Latency vs bandwidth.
- Connection pooling.
- Load balancing.
- Reverse proxies.
- Timeouts, retries, exponential backoff.
- Idempotency.
- Authentication và authorization.

## 3. Data Engineering & Data Foundations

Mức độ: Core

### 3.1. Data Manipulation

- NumPy arrays và broadcasting.
- Pandas DataFrames.
- Polars.
- PyArrow.
- Vectorized operations.
- Missing values và duplicated data.
- Type conversion.
- Grouping, joins, aggregations.
- Large dataset processing.
- Memory-efficient data loading.

### 3.2. SQL & Databases

- SELECT, JOIN, GROUP BY, HAVING.
- Subqueries và CTEs.
- Window functions.
- Indexes và query planning.
- ACID transactions.
- Isolation levels.
- Database normalization.
- PostgreSQL.
- Redis.
- NoSQL fundamentals.
- OLTP vs OLAP.
- Data partitioning.

### 3.3. Data Storage

- CSV, JSON, JSONL.
- Parquet, Arrow, Avro.
- Object storage: S3-compatible storage, GCS, Azure Blob.
- Data lakes, warehouses, lakehouses.
- Compression và encoding.
- Schema evolution.
- Partitioning và bucketing.
- Data retention và versioning.

### 3.4. ETL / ELT Pipelines

- Extract, Transform, Load.
- Batch processing vs streaming.
- Data ingestion.
- Apache Airflow, Dagster.
- Apache Spark.
- Kafka và event streaming.
- Change Data Capture (CDC).
- Orchestration, retries, backfills.
- Pipeline monitoring.
- Idempotent data processing.

### 3.5. Data Quality & Governance

- Data profiling.
- Schema validation.
- Missing-value analysis.
- Anomaly detection.
- Duplicate detection.
- Data leakage.
- Label noise.
- Data drift.
- Data lineage.
- Dataset versioning.
- Great Expectations hoặc tương đương.
- Data contracts.
- PII identification và sensitive data handling.

### 3.6. Data Annotation & Dataset Construction

- Annotation workflows.
- Labeling guidelines.
- Inter-annotator agreement.
- Human review.
- Weak supervision.
- Active learning.
- Synthetic data generation.
- Class balancing.
- Training, validation và test splits.
- Dataset representativeness.
- Data provenance và licensing.

## 4. Traditional Machine Learning

Mức độ: Core

### 4.1. ML Paradigms

- Supervised learning.
- Unsupervised learning.
- Semi-supervised learning.
- Self-supervised learning.
- Reinforcement learning foundations.
- Online vs offline learning.
- Batch vs incremental training.
- Classification, regression, ranking, clustering.

### 4.2. Regression Algorithms

- Linear Regression.
- Ridge Regression.
- Lasso Regression.
- Elastic Net.
- Logistic Regression.
- Polynomial Regression.
- Loss functions: MSE, MAE, Huber, log loss.
- Regularization.
- Model assumptions và diagnostics.

### 4.3. Classification Algorithms

- K-Nearest Neighbors.
- Naive Bayes.
- Decision Trees.
- Random Forest.
- Support Vector Machines.
- Gradient Boosting.
- XGBoost, LightGBM, CatBoost.
- Class imbalance.
- Decision thresholds và probability calibration.

### 4.4. Unsupervised Learning

- K-Means.
- Hierarchical clustering.
- DBSCAN và HDBSCAN.
- Gaussian Mixture Models.
- PCA.
- t-SNE.
- UMAP.
- Isolation Forest.
- Anomaly detection.
- Association rules.

### 4.5. Feature Engineering

- Encoding categorical variables.
- Feature scaling.
- Standardization và normalization.
- Missing value imputation.
- Feature selection.
- Feature extraction.
- Polynomial và interaction features.
- Handling outliers.
- Time-based features.
- Leakage prevention.

### 4.6. Model Evaluation

- Confusion matrix.
- Accuracy, precision, recall, F1.
- Macro, micro, weighted averaging.
- ROC-AUC và PR-AUC.
- Log loss và calibration.
- Regression: MAE, RMSE, R², MAPE.
- Cross-validation.
- Stratified splitting.
- Time-series validation.
- Bias-variance trade-off.
- Underfitting và overfitting.
- Error analysis theo từng nhóm dữ liệu.

### 4.7. Hyperparameter Optimization

- Grid search.
- Random search.
- Bayesian optimization.
- Optuna.
- Hyperband và early stopping.
- Learning curves.
- Experiment tracking.
- Reproducibility.
- Resource-aware tuning.

### 4.8. ML Interpretability

- Feature importance.
- Permutation importance.
- SHAP.
- LIME.
- Partial dependence plots.
- Calibration curves.
- Local vs global explanations.
- Causal limitations of explanations.

# PHẦN II. DEEP LEARNING & MODEL ARCHITECTURES

## 5. Deep Learning Fundamentals

Mức độ: Core

### 5.1. Neural Network Basics

- Perceptron.
- Multilayer Perceptron (MLP).
- Neurons, weights, biases.
- Forward propagation.
- Backward propagation.
- Computational graphs.
- Activation functions: Sigmoid, Tanh, ReLU, LeakyReLU, GELU, SiLU.
- Universal approximation concept.
- Neural network parameter counting.

### 5.2. Loss Functions

- MSE, MAE.
- Binary Cross-Entropy.
- Categorical Cross-Entropy.
- Focal Loss.
- Dice Loss, IoU Loss.
- Contrastive Loss.
- Triplet Loss.
- KL Divergence.
- Label smoothing.
- Multi-task loss weighting.

### 5.3. Training Mechanics

- Epoch, batch, iteration.
- Mini-batch SGD.
- Forward → Loss → Backward → Optimizer Step.
- Gradient accumulation.
- Learning rate warmup và decay.
- Weight initialization: Xavier, Kaiming.
- Gradient clipping.
- Early stopping.
- Checkpointing.
- Random seeds và reproducibility.
- Gradient vanishing và exploding.
- Training/validation loss analysis.

### 5.4. Regularization & Normalization

- L1/L2 regularization.
- Dropout.
- Batch Normalization.
- Layer Normalization.
- RMSNorm.
- Group Normalization.
- Weight decay.
- Data augmentation.
- Stochastic depth.
- Residual connections.

### 5.5. PyTorch Ecosystem

- Tensor operations.
- Autograd.
- `nn.Module`.
- `Dataset`, `DataLoader`.
- Custom loss functions.
- Custom training loops.
- Optimizers và schedulers.
- TorchMetrics.
- Automatic Mixed Precision (AMP).
- `torch.compile`.
- Gradient checkpointing.
- CUDA device management.
- Model checkpoint save/load.
- PyTorch profiler.
- Custom autograd functions (Advanced).

### 5.6. Debugging Deep Learning

- Kiểm tra tensor shapes.
- Gradient inspection.
- NaN và Inf loss.
- Exploding gradients.
- GPU Out of Memory.
- Learning rate instability.
- Incorrect model mode (`train` vs `eval`).
- Data normalization mismatch.
- Silent broadcasting errors.
- Reproducibility bugs.
- Overfit một batch nhỏ để kiểm chứng pipeline.
- Train/evaluation distribution mismatch.

## 6. Deep Learning Architectures

Mức độ: Core → Working

### 6.1. Convolutional Neural Networks

- Convolution operation.
- Kernels và filters.
- Stride, padding, dilation.
- Feature maps.
- Receptive fields.
- Pooling: max, average, global.
- Depthwise separable convolution.
- 1×1 convolution.
- Residual connections.
- Skip connections.
- FLOPs và parameter calculations.

### 6.2. CNN Architectures

- LeNet.
- AlexNet.
- VGG.
- Inception / GoogLeNet.
- ResNet.
- DenseNet.
- EfficientNet.
- MobileNet.
- ConvNeXt.
- Squeeze-and-Excitation (SE).
- Feature Pyramid Networks (FPN).

### 6.3. Recurrent Neural Networks

- Vanilla RNN.
- Hidden states.
- LSTM.
- GRU.
- Bidirectional RNN.
- Encoder-Decoder.
- Sequence-to-sequence learning.
- Teacher forcing.
- Vanishing gradients in recurrent models.

### 6.4. Attention Mechanisms

- Attention intuition.
- Query, Key, Value.
- Scaled Dot-Product Attention.
- Self-Attention.
- Cross-Attention.
- Multi-Head Attention.
- Causal masking.
- Padding masks.
- Attention complexity.
- Attention visualization.
- FlashAttention concepts.

### 6.5. Transformer Architecture

- Transformer Encoder.
- Transformer Decoder.
- Encoder-Decoder Transformers.
- Positional encoding.
- Rotary Position Embedding (RoPE).
- Relative positional representations.
- Feedforward networks.
- Residual pathways.
- Pre-Norm vs Post-Norm.
- Causal Language Modeling.
- Masked Language Modeling.
- KV Cache.
- Context length.
- Grouped Query Attention (GQA).
- Multi-Query Attention (MQA).
- Sliding Window Attention.
- Sparse attention.
- Mixture of Experts (MoE).

### 6.6. Representation Learning

- Embeddings.
- Latent spaces.
- Autoencoders.
- Variational Autoencoders (VAE).
- Siamese networks.
- Contrastive learning.
- SimCLR, MoCo, BYOL.
- CLIP và image-text alignment.
- Metric learning.
- Self-supervised pretraining.

### 6.7. Generative Architectures

- Autoregressive models.
- Variational Autoencoders.
- Generative Adversarial Networks (GANs).
- Diffusion Models.
- Latent Diffusion.
- Diffusion Transformers (DiT).
- Flow Matching.
- Rectified Flow.
- Consistency models.
- Autoregressive vs diffusion generation.

## 7. Computer Vision Engineering

Mức độ: Working • Core nếu theo Computer Vision

### 7.1. Image Processing

- Pixels, color spaces: RGB, HSV, LAB, grayscale.
- Image resizing, cropping, padding.
- Image interpolation.
- Histogram và contrast enhancement.
- Gaussian, median, bilateral filters.
- Edge detection: Sobel, Canny.
- Morphological operations.
- Image transformations.
- OpenCV, Pillow, torchvision.
- Image compression và quality degradation.

### 7.2. Image Classification

- Single-label vs multi-label classification.
- Transfer learning.
- Fine-tuning pretrained CNN/ViT.
- Class imbalance.
- Threshold tuning.
- Grad-CAM.
- Domain shift.
- Robustness với noise, blur, ánh sáng và góc chụp.

### 7.3. Object Detection

- Bounding boxes.
- IoU và Non-Maximum Suppression (NMS).
- Anchor-based vs anchor-free detection.
- One-stage vs two-stage detectors.
- Faster R-CNN.
- YOLO families.
- DETR và transformer-based detection.
- Object detection metrics: mAP\@IoU.
- Small object detection.

### 7.4. Segmentation

- Semantic segmentation.
- Instance segmentation.
- Panoptic segmentation.
- U-Net, U-Net++.
- DeepLab.
- Mask R-CNN.
- Segment Anything Model (SAM) families.
- Dice, IoU, pixel accuracy.
- Boundary-aware losses.
- Postprocessing masks.

### 7.5. Vision Transformers & Multimodal Vision

- Vision Transformer (ViT).
- Patch embeddings.
- Swin Transformer.
- DINO và self-supervised vision encoders.
- Image-text embeddings.
- CLIP-like architectures.
- Grounding và phrase localization.
- Vision-Language Models (VLMs).
- Document vision và visual question answering.

### 7.6. Advanced Computer Vision

- Image restoration.
- Super-resolution.
- OCR.
- Document layout analysis.
- Image registration.
- Depth estimation.
- Optical flow.
- Object tracking.
- Pose estimation.
- 3D reconstruction.
- Camera calibration.
- Real-time edge vision.

## 8. NLP, Speech & Sequential Data

Mức độ: Working

### 8.1. Traditional NLP

- Text cleaning và normalization.
- Tokenization.
- Stopword handling.
- Stemming và lemmatization.
- N-grams.
- Bag of Words.
- TF-IDF.
- Text classification.
- Named Entity Recognition.
- Part-of-Speech tagging.
- Topic modeling.

### 8.2. Semantic Representations

- Word2Vec.
- GloVe.
- FastText.
- Contextual embeddings.
- Sentence embeddings.
- Cosine similarity.
- Semantic similarity.
- Cross-encoders.
- Bi-encoders.
- Multilingual embeddings.

### 8.3. Modern NLP Tasks

- Text classification.
- Information extraction.
- Entity linking.
- Summarization.
- Question answering.
- Machine translation.
- Text generation.
- Sentiment analysis.
- Natural Language Inference.
- Semantic search.

### 8.4. Speech AI

- Digital audio và sample rates.
- Waveforms, STFT, mel spectrogram.
- Automatic Speech Recognition (ASR).
- Text-to-Speech (TTS).
- Voice Activity Detection (VAD).
- Speaker diarization.
- Speaker identification.
- Speech enhancement.
- Voice conversion.
- Real-time speech streaming.
- Word Error Rate (WER), Character Error Rate (CER).
- Speech-to-speech models.

### 8.5. Time-Series Modeling

- Stationarity.
- Trends, seasonality.
- Autocorrelation.
- ARIMA, SARIMA.
- Exponential smoothing.
- LSTM/GRU forecasting.
- Transformer-based forecasting.
- Time-series anomaly detection.
- Rolling windows và leakage prevention.
- Forecast evaluation.

# PHẦN III. GENERATIVE AI & LLM ENGINEERING

Đây là một trong những phần quan trọng nhất với AI Engineer thiên về sản phẩm trong năm 2026.

## 9. Large Language Model Fundamentals

Mức độ: Core

### 9.1. LLM Architecture

- Decoder-only Transformers.
- Encoder-only vs Encoder-Decoder.
- Autoregressive generation.
- Causal attention.
- Token embeddings.
- Attention blocks.
- Feedforward blocks.
- RMSNorm, RoPE, SwiGLU.
- Weight tying.
- Dense vs Sparse/MoE models.
- Model parameters vs active parameters.

### 9.2. Tokenization

- Byte Pair Encoding (BPE).
- WordPiece.
- SentencePiece.
- Byte-level tokenization.
- Special tokens.
- Chat templates.
- Token counting.
- Vocabulary size.
- Tokenization overhead.
- Tokenizer compatibility khi fine-tuning và serving.

### 9.3. LLM Pretraining

- Next-token prediction.
- Pretraining objectives.
- Web/document/code datasets.
- Data deduplication.
- Dataset mixture.
- Data contamination.
- Curriculum learning.
- Compute-optimal training và scaling laws.
- Training loss và perplexity.
- Checkpoint selection.

### 9.4. Inference & Text Generation

- Logits.
- Softmax.
- Greedy decoding.
- Temperature.
- Top-k sampling.
- Top-p / nucleus sampling.
- Min-p sampling.
- Repetition penalty.
- Presence/frequency penalties.
- Stop sequences.
- Beam search.
- Constrained decoding.
- Structured generation.
- Reasoning-token và output-token budgets.

### 9.5. Reasoning Models

- Inference-time compute.
- Test-time scaling.
- Deliberation và reasoning budgets.
- Verifiers.
- Self-consistency.
- Best-of-N sampling.
- Search-based reasoning.
- Process vs outcome rewards.
- Reasoning distillation.
- Tool-assisted reasoning.
- Accuracy-latency trade-offs.

### 9.6. LLM Model Families & Architectures

- GPT-style dense Transformers.
- Llama-style open-weight models.
- Qwen-style multilingual/coding models.
- Mixture-of-Experts architectures.
- Multimodal language models.
- State Space Models.
- Mamba.
- Hybrid attention/SSM architectures.
- Long-context models.
- Small Language Models (SLMs).
- Model cards, licensing, benchmarks.

### 9.7. LLM Failure Modes

- Hallucinations.
- Knowledge cutoff.
- Context loss.
- Long-context degradation.
- Lost-in-the-middle effects.
- Instruction conflicts.
- Tool-call errors.
- Numerical reasoning errors.
- Model bias.
- Nondeterministic output.
- Unsupported factual claims.
- Overconfidence.

## 10. Prompt Engineering & Context Engineering

Mức độ: Core

### 10.1. Prompt Fundamentals

- System, developer và user instructions.
- Roles và instruction hierarchy.
- Zero-shot prompting.
- Few-shot prompting.
- Clear task specifications.
- Output constraints.
- Examples và counterexamples.
- Prompt templates.
- Prompt versioning.
- Prompt regression testing.

### 10.2. Advanced Prompting

- Chain-of-Thought prompting as a technique.
- Self-consistency.
- ReAct pattern.
- Plan-and-execute.
- Decomposition.
- Prompt chaining.
- Self-critique và verification.
- Structured reasoning workflows.
- Distinguishing user-facing explanations from private model reasoning.

### 10.3. Structured Outputs

- JSON Schema.
- Pydantic models.
- Function calling.
- Tool argument schemas.
- Constrained decoding.
- Schema validation.
- Invalid-output recovery.
- Optional fields, unions và enums.
- Output contracts.
- Type-safe LLM integration.

### 10.4. Context Window Management

- Token budgeting.
- Context truncation.
- Summarization.
- Context compression.
- Relevant-context selection.
- Prompt caching.
- Context deduplication.
- Long-context trade-offs.
- Multi-document context construction.
- Context overflow handling.

### 10.5. Context Engineering

- Dynamic context assembly.
- Instructions vs knowledge vs memory.
- Retrieval-augmented context.
- Tool result filtering.
- User-profile/context injection with consent.
- State management.
- Short-term memory.
- Long-term memory.
- Memory retrieval.
- Memory consolidation và expiration.
- Provenance tracking cho context.
- Preventing context poisoning.

### 10.6. Prompt Optimization

- Prompt evaluation datasets.
- A/B prompt comparisons.
- Prompt sensitivity.
- Model-specific prompting.
- Prompt optimizer workflows.
- Failure-case clustering.
- Evaluation-driven prompt iteration.
- Cost and latency impact of prompt length.

## 11. Embeddings, Search & Retrieval-Augmented Generation

Mức độ: Core

### 11.1. Information Retrieval Foundations

- Lexical search.
- TF-IDF.
- BM25.
- Dense retrieval.
- Sparse neural retrieval.
- Hybrid search.
- Semantic search.
- Cosine similarity, dot product, L2 distance.
- Precision\@K, Recall\@K.
- MRR và NDCG.

### 11.2. Embedding Models

- Embedding generation.
- Sentence Transformers.
- Embedding dimensions.
- Normalization.
- Multilingual embeddings.
- Domain-specific embeddings.
- Query-document asymmetry.
- Embedding drift.
- Model upgrades và re-indexing.
- Embedding quality benchmarks.

### 11.3. Vector Databases

- FAISS.
- Milvus.
- Qdrant.
- Weaviate.
- Pinecone.
- pgvector.
- Elasticsearch/OpenSearch vector capabilities.
- Similarity indexes.
- HNSW.
- IVF.
- Product Quantization.
- Metadata filters.
- Index updates và deletes.
- Multi-tenant indexing.

### 11.4. Document Ingestion

- PDF parsing.
- HTML parsing.
- DOCX processing.
- OCR.
- Table extraction.
- Layout-aware extraction.
- Header/footer removal.
- Document metadata.
- Document versioning.
- Incremental ingestion.
- Deduplication.
- Document access permissions.

### 11.5. Chunking Strategies

- Fixed-size chunking.
- Recursive chunking.
- Sentence-based chunking.
- Semantic chunking.
- Document-aware chunking.
- Hierarchical chunking.
- Parent-child retrieval.
- Chunk overlap.
- Metadata enrichment.
- Contextual chunk augmentation.
- Tuning chunk size dựa trên evaluation.

### 11.6. RAG Pipeline Architecture

- Query preprocessing.
- Query rewriting.
- Query expansion.
- Query decomposition.
- Query routing.
- Retrieval.
- Candidate fusion.
- Reranking.
- Context assembly.
- LLM generation.
- Citation grounding.
- Abstention khi thiếu bằng chứng.

### 11.7. Advanced RAG

- Hybrid RAG.
- Multi-query RAG.
- Multi-hop retrieval.
- Self-RAG concepts.
- Corrective RAG (CRAG).
- Adaptive RAG.
- Agentic RAG.
- GraphRAG.
- Knowledge Graph RAG.
- Hierarchical retrieval.
- Multi-vector retrieval.
- Multimodal RAG.
- SQL-based RAG.
- Retrieval with temporal validity.

### 11.8. RAG Evaluation & Debugging

- Context precision.
- Context recall.
- Faithfulness.
- Answer relevance.
- Groundedness.
- Citation accuracy.
- Retrieval latency.
- No-answer/abstention accuracy.
- Hallucination analysis.
- Evaluating retriever vs generator separately.
- Golden test datasets.
- Evaluating document freshness.

Những metric như Context Precision, Context Recall, Faithfulness và Response Relevancy đã có trong các bộ công cụ đánh giá RAG, nhưng cần hiểu chính xác từng metric đo cái gì thay vì chỉ nhìn một điểm số tổng.&#x20;

[image](https://www.google.com/s2/favicons?domain=https://docs.ragas.io\&sz=32)

Ragas

+1



### 11.9. Production RAG

- Incremental indexing.
- Document update/delete propagation.
- Permission-aware retrieval.
- Tenant isolation.
- Embedding caching.
- Retrieval caching.
- Retrieval monitoring.
- Vector database backup.
- Index migration.
- Multi-stage retrieval performance.
- Storage cost optimization.
- Security of retrieved documents.

## 12. AI Agents & Agentic Workflows

Mức độ: Core → Working

Agent Engineering ở mốc 2026 cần học cả orchestration, state, tool contracts, runtime security, tracing, recovery và evaluation, không chỉ học một framework rồi ghép nhiều agent thành sơ đồ. SDK hiện đại đã tích hợp tool use, orchestration, human review và tracing như những thành phần chính.&#x20;

[image](https://www.google.com/s2/favicons?domain=https://developers.openai.com\&sz=32)

OpenAI API

+1



### 12.1. Agent Fundamentals

- LLM vs Workflow vs Agent.
- Deterministic vs nondeterministic execution.
- Agent loop.
- Planning.
- Acting.
- Observation.
- Reflection.
- Tool selection.
- Termination conditions.
- Agent state.
- Success criteria.

### 12.2. Agent Workflow Patterns

- Prompt chaining.
- Routing.
- Parallelization.
- Orchestrator-worker.
- Evaluator-optimizer.
- ReAct.
- Plan-and-execute.
- Reflection loops.
- Map-reduce agent workflows.
- Iterative refinement.
- Autonomous vs controlled workflows.

### 12.3. Tool Calling

- Function calling.
- Tool schemas.
- JSON arguments.
- Tool descriptions.
- Tool choice.
- Tool-result interpretation.
- Parallel tool calls.
- Tool retries.
- Tool timeouts.
- Tool error recovery.
- Idempotent tool operations.
- Read-only vs write-capable tools.

### 12.4. Agent State & Memory

- Ephemeral state.
- Persistent state.
- Conversation state.
- Working memory.
- Long-term memory.
- Checkpointing.
- State serialization.
- Resumable execution.
- Memory expiration.
- User-specific memory isolation.
- Memory correctness và conflict handling.

### 12.5. Human-in-the-Loop

- Approval gates.
- Interrupt/resume.
- Tool approval.
- Reviewable action plans.
- Manual override.
- Escalation policies.
- Human feedback integration.
- Audit trails.
- Reversible operations.
- Irreversible action protection.

### 12.6. Multi-Agent Systems

- Supervisor-worker systems.
- Planner-executor.
- Researcher-reviewer.
- Agent delegation.
- Handoffs.
- Agent communication.
- Shared vs isolated memory.
- Distributed agent execution.
- Deadlocks và circular handoffs.
- Coordination overhead.
- Multi-agent cost evaluation.

### 12.7. Agent Frameworks

- OpenAI Agents SDK.
- LangGraph.
- LangChain agent ecosystem.
- Google Agent Development Kit (ADK).
- CrewAI.
- Semantic Kernel.
- AutoGen.
- Custom agent runtimes.
- Framework abstraction vs direct API design.
- When not to use a framework.

### 12.8. Model Context Protocol (MCP)

- MCP architecture.
- Host, Client, Server.
- JSON-RPC.
- Resources.
- Tools.
- Prompts.
- STDIO transport.
- HTTP transport.
- Discovery và capability negotiation.
- Tool/resource permissions.
- Authentication và OAuth-based authorization.
- Version compatibility.
- Error handling.
- Secure MCP server implementation.

MCP đã có bản specification 2026-07-28, bổ sung stateless protocol core, Multi Round-Trip Requests, cải thiện authorization và cơ chế extensions. Do đó, kiến thức MCP chỉ dừng ở ví dụ tool calling cũ là chưa đủ.&#x20;

[image](https://www.google.com/s2/favicons?domain=https://blog.modelcontextprotocol.io\&sz=32)

Model Context Protocol Blog

+2



### 12.9. Agent-to-Agent Protocol (A2A)

- Agent discovery.
- Agent identity.
- Agent capabilities.
- Agent Cards.
- Task lifecycle.
- Inter-agent messages.
- Streaming task updates.
- Asynchronous operations.
- Artifacts.
- Authentication.
- Agent interoperability.
- A2A vs MCP.

Phân biệt quan trọng: MCP chủ yếu tiêu chuẩn hóa việc kết nối agent/application với tools và data; A2A tập trung vào giao tiếp giữa các agent như những hệ thống độc lập.&#x20;

[image](https://www.google.com/s2/favicons?domain=https://a2a-protocol.org\&sz=32)

A2A Protocol

+1



### 12.10. Agent Runtime & Execution

- Durable execution.
- Long-running tasks.
- Checkpoints.
- Retry policies.
- Timeout budgets.
- Cancellation.
- Task queues.
- Async execution.
- Sandbox execution.
- Filesystem operations.
- Browser/computer use.
- Execution isolation.
- Resource quotas.

### 12.11. Agent Reliability

- Tool failure recovery.
- Infinite-loop detection.
- Budget exhaustion.
- Maximum steps.
- Replanning.
- Fallback models.
- State recovery.
- Duplicate actions.
- Partial completion.
- Graceful degradation.
- Circuit breakers.
- Human escalation.

### 12.12. Agent Evaluation

- Task completion rate.
- Tool-call accuracy.
- Argument correctness.
- Trajectory evaluation.
- Tool efficiency.
- Agent path length.
- Cost per successful task.
- End-to-end latency.
- Human intervention frequency.
- Side-effect correctness.
- Recovery rate.
- Unauthorized-action rate.

### 12.13. Advanced Agent Systems

- Coding agents.
- Browser agents.
- Computer-use agents.
- Research agents.
- Data analysis agents.
- Multi-agent delegation across services.
- Long-horizon planning.
- Environment interaction.
- Agent reinforcement learning.
- Learned tool-selection policies.
- Agent self-improvement under evaluation constraints.

## 13. LLM Evaluation, Testing & Observability

Mức độ: Core • Đặc biệt quan trọng ở Middle

Evaluation là phần tôi xếp cao hơn việc biết thêm mười framework. Hướng dẫn đánh giá hiện hành nhấn mạnh task-specific evals, human calibration, regression testing và continuous evaluation, thay vì chấm model theo cảm giác hoặc chỉ sử dụng một public benchmark.&#x20;

[image](https://www.google.com/s2/favicons?domain=https://developers.openai.com\&sz=32)

OpenAI API

+1



### 13.1. Evaluation Fundamentals

- Offline vs online evaluation.
- Intrinsic vs extrinsic metrics.
- Model-level vs system-level evaluation.
- Test sets.
- Golden datasets.
- Representative sampling.
- Human evaluation.
- Model comparison.
- Evaluation reproducibility.
- Benchmark contamination.

### 13.2. Classical NLP/LLM Metrics

- Perplexity.
- Exact Match.
- BLEU.
- ROUGE.
- METEOR.
- BERTScore.
- Semantic similarity.
- Classification metrics.
- Task-specific exactness.
- Limitations of automatic metrics.

### 13.3. LLM-as-a-Judge

- Rubric-based evaluation.
- Pointwise scoring.
- Pairwise comparison.
- Reference-guided evaluation.
- Position bias.
- Verbosity bias.
- Judge-model selection.
- Calibration with human labels.
- Inter-judge agreement.
- Judge drift.

### 13.4. RAG & Agent Evaluation

- Retrieval-level evaluation.
- Generator-level evaluation.
- End-to-end RAG evaluation.
- Tool selection accuracy.
- Tool argument accuracy.
- Trajectory correctness.
- Agent goal completion.
- Groundedness.
- Multi-step task evaluation.
- Side-effect validation.

### 13.5. Robustness & Red Team Testing

- Adversarial prompts.
- Prompt injection tests.
- Jailbreak attempts.
- Out-of-distribution inputs.
- Multilingual edge cases.
- Long-context stress tests.
- Invalid tool outputs.
- Ambiguous instructions.
- Malformed structured input.
- Failure-injection testing.

### 13.6. Experimentation & Regression

- Baseline establishment.
- Controlled experiments.
- Prompt/model version comparisons.
- A/B tests.
- Canary evaluation.
- Shadow testing.
- Continuous evaluation.
- Statistical confidence.
- Failure taxonomy.
- Evaluation gates trong CI/CD.

### 13.7. Observability

- Structured logs.
- Distributed traces.
- Agent trajectory traces.
- Prompt/completion logging with privacy controls.
- Tool call tracing.
- Token usage.
- Model response latency.
- Error categorization.
- Metrics dashboards.
- OpenTelemetry GenAI conventions.
- Langfuse, LangSmith, Phoenix và tương đương.

### 13.8. Production AI Metrics

- Task success rate.
- User acceptance rate.
- Hallucination rate.
- Failure rate.
- P50/P95/P99 latency.
- Request throughput.
- Tokens per second.
- Token cost.
- Cost per successful task.
- Retrieval hit rate.
- Tool failure rate.
- Safety violation rate.

# PHẦN IV. MODEL TRAINING, FINE-TUNING & OPTIMIZATION

## 14. Fine-Tuning & Post-Training

Mức độ: Working • Core với AI Engineer thiên về model

### 14.1. Transfer Learning

- Feature extraction.
- Freezing pretrained layers.
- Partial unfreezing.
- Full fine-tuning.
- Layer-wise learning rates.
- Domain adaptation.
- Catastrophic forgetting.
- Model initialization.
- Choosing pretrained checkpoints.

### 14.2. Supervised Fine-Tuning (SFT)

- Instruction datasets.
- Prompt-completion pairs.
- Conversational datasets.
- Chat templates.
- Loss masking.
- Packing sequences.
- Sequence truncation.
- Dataset cleaning.
- SFT hyperparameters.
- Evaluation before/after fine-tuning.

### 14.3. Parameter-Efficient Fine-Tuning (PEFT)

- Adapters.
- LoRA.
- QLoRA.
- LoRA rank và alpha.
- Target modules.
- Adapter merging.
- Multi-adapter serving.
- IA³.
- DoRA.
- Prefix tuning.
- Prompt tuning.
- Memory/performance trade-offs.

### 14.4. Preference Optimization

- RLHF principles.
- Preference datasets.
- Reward models.
- Bradley-Terry preference model.
- Direct Preference Optimization (DPO).
- IPO, KTO và các phương pháp liên quan.
- Reward hacking.
- Preference data quality.
- Safety/helpfulness trade-offs.

### 14.5. Reinforcement Learning for LLMs

- Markov Decision Processes.
- Policies, rewards và trajectories.
- Policy gradients.
- REINFORCE.
- Actor-Critic.
- PPO.
- GRPO.
- RLOO.
- Rule-based rewards.
- Verifiable rewards.
- KL regularization.
- On-policy vs off-policy optimization.
- Training instability.
- Reward exploitation.
- RL for reasoning/tool use.

### 14.6. Distillation

- Teacher-student architecture.
- Knowledge distillation.
- Logit distillation.
- Feature distillation.
- Sequence-level distillation.
- Response distillation.
- Reasoning distillation.
- Dataset synthesis from stronger models.
- Quality vs model size trade-off.

### 14.7. Efficient Fine-Tuning

- Mixed precision.
- Gradient accumulation.
- Gradient checkpointing.
- CPU offloading.
- Optimizer state optimization.
- FlashAttention-compatible training.
- Quantized model loading.
- Distributed fine-tuning.
- Low-memory training.
- Checkpoint resumption.

### 14.8. Fine-Tuning Decision Making

- Prompting vs RAG vs fine-tuning.
- Domain specialization.
- Knowledge injection vs behavioral adaptation.
- Data requirements.
- Training cost.
- Deployment overhead.
- Evaluation and regression risks.
- Choosing a base model.
- When fine-tuning is unnecessary.

Về công cụ, Hugging Face TRL hiện hỗ trợ các nhóm huấn luyện quan trọng như SFT, DPO, GRPO, RLOO, Reward Modeling và Distillation. Với Middle AI Engineer, SFT/LoRA/QLoRA nên biết thực hành; các phương pháp RL phức tạp có thể học sâu tùy công việc.&#x20;

[image](https://www.google.com/s2/favicons?domain=https://huggingface.co\&sz=32)

Hugging Face

+1



## 15. LLM Inference Engineering & Model Serving

Mức độ: Core → Working

### 15.1. Inference Fundamentals

- Prefill phase.
- Decode phase.
- Autoregressive decoding.
- Compute-bound vs memory-bandwidth-bound operations.
- GPU memory usage.
- Model weights.
- Activations.
- KV Cache.
- Inference batch size.
- Concurrency.
- Latency vs throughput.

### 15.2. GPU Memory Management

- VRAM allocation.
- CUDA memory allocator.
- Fragmentation.
- Model weight footprint.
- Activation memory.
- KV Cache memory.
- Peak memory.
- Memory profiling.
- Memory offloading.
- CUDA Out of Memory debugging.

### 15.3. Attention Optimization

- Standard attention.
- FlashAttention.
- PagedAttention.
- KV Cache management.
- Prefix caching.
- Sliding-window attention.
- Chunked prefill.
- Attention kernels.
- KV Cache eviction.
- KV Cache quantization.
- KV Cache reuse.

### 15.4. Batching & Scheduling

- Static batching.
- Dynamic batching.
- Continuous batching.
- Request scheduling.
- Prefill scheduling.
- Decode scheduling.
- Token budgets.
- Admission control.
- Request prioritization.
- Head-of-line blocking.
- Tail latency management.

### 15.5. Speculative Decoding

- Draft model và target model.
- Proposal and verification.
- Exactness-preserving speculative sampling.
- Acceptance rate.
- Rejection overhead.
- Speculative speedup.
- N-gram speculation.
- Medusa.
- EAGLE family.
- Multi-token prediction.
- Self-speculative decoding.
- When speculative decoding becomes slower.

### 15.6. Long-Context Inference

- Context window scaling.
- KV memory scaling.
- RoPE scaling.
- Long-context positional strategies.
- Sliding window inference.
- Chunked prefill.
- Prefix caching.
- Context parallelism.
- Memory-bandwidth trade-offs.
- Long-context quality evaluation.

### 15.7. Production Serving Engines

- vLLM.
- SGLang.
- TensorRT-LLM.
- llama.cpp.
- Ollama.
- Hugging Face Transformers serving.
- Triton Inference Server.
- Text Generation Inference concepts.
- OpenAI-compatible APIs.
- Choosing engines based on hardware, workload và supported features.

### 15.8. Serving Performance Metrics

- Time To First Token (TTFT).
- Time Per Output Token (TPOT).
- Inter-Token Latency (ITL).
- End-to-end latency.
- Prefill throughput.
- Decode throughput.
- Tokens/second.
- Requests/second.
- GPU utilization.
- KV Cache utilization.
- Queueing delay.
- P50/P95/P99 response time.

### 15.9. Advanced Serving Architectures

- Tensor parallel inference.
- Pipeline parallel inference.
- Expert parallelism.
- Data-parallel replicas.
- Disaggregated prefill/decode.
- KV Cache transfer.
- Multi-node serving.
- Load-aware routing.
- Heterogeneous GPU placement.
- Cost-aware scheduling.

### 15.10. Disaggregated Serving

- Prefill vs decode workload characteristics.
- Independent scaling of prefill workers.
- Independent scaling of decode workers.
- KV Cache transport.
- TTFT/ITL optimization.
- GPU-less frontend concepts.
- Queue management.
- Distributed scheduling.
- When splitting workloads is counterproductive.

Đây là chủ đề đáng chú ý vào 10/2026: vLLM đã công bố hướng dẫn kỹ thuật về disaggregated serving ngày 29/09/2026, trong đó tách prefill, decode và một phần xử lý frontend để quản lý tài nguyên hiệu quả hơn. Tuy vậy, một số khả năng vẫn đang phát triển, không nên mặc định chúng luôn tốt hơn serving truyền thống.&#x20;

[image](https://www.google.com/s2/favicons?domain=https://vllm-project.github.io\&sz=32)

vLLM Blog

+1



## 16. Quantization & Model Compression

Mức độ: Working • Advanced với Inference Optimization Engineer

### 16.1. Numerical Representations

- FP32.
- FP16.
- BF16.
- TF32.
- FP8 E4M3, E5M2.
- INT8.
- INT4.
- FP4 E2M1.
- MXFP8.
- MXFP4.
- NVFP4.
- Signed vs unsigned integers.
- Floating-point dynamic range.
- Precision vs representable range.

### 16.2. Quantization Mathematics

- Quantization scale.
- Zero-point.
- Symmetric vs asymmetric quantization.
- Uniform vs non-uniform quantization.
- Per-tensor quantization.
- Per-channel quantization.
- Per-group quantization.
- Per-block quantization.
- Static vs dynamic quantization.
- Quantization error.
- Clipping.
- Outlier handling.
- Rounding modes.

### 16.3. Quantization Techniques

- Post-Training Quantization (PTQ).
- Quantization-Aware Training (QAT).
- Dynamic quantization.
- Weight-only quantization.
- Weight-activation quantization.
- Calibration-based quantization.
- Calibration-free precision casting.
- Mixed-precision quantization.
- Activation smoothing.
- Layer-wise sensitivity analysis.

### 16.4. LLM Quantization Algorithms

- GPTQ.
- AWQ.
- SmoothQuant.
- bitsandbytes LLM.int8.
- NF4.
- GGUF quantization schemes.
- EXL2 concepts.
- HQQ.
- AutoRound.
- Quantization-aware adapters.
- Activation outlier mitigation.

### 16.5. FP8 / FP4 Inference

- FP8 weight representation.
- FP8 activation scaling.
- E4M3 vs E5M2 trade-offs.
- FP8 GEMM.
- FP8 KV Cache.
- FP4 weight formats.
- NVFP4 block scaling.
- MXFP4 microscaling.
- Quantization metadata overhead.
- Hardware-native low-precision kernels.
- Accuracy and speed validation.

### 16.6. Calibration

- Representative calibration datasets.
- Calibration dataset size.
- Activation statistics.
- Min-max calibration.
- Percentile clipping.
- Outlier sensitivity.
- Distribution mismatch.
- Per-layer calibration.
- Evaluating rare and long-context cases.

### 16.7. Model Compression

- Unstructured pruning.
- Structured pruning.
- Sparsity.
- N:M sparsity.
- Low-rank approximation.
- Weight sharing.
- Knowledge distillation.
- Layer removal.
- Width/depth reduction.
- Model merging.
- Compression combinations.

### 16.8. Quantization Evaluation

- Perplexity comparison.
- Task accuracy.
- Hallucination regression.
- Reasoning degradation.
- Coding benchmark regression.
- Long-context robustness.
- Memory reduction.
- Tokens/sec.
- Latency.
- Quantized kernel compatibility.
- Cost-quality Pareto frontier.

### 16.9. Quantization Deployment

- Model export formats.
- Quantization metadata.
- Kernel support.
- TensorRT.
- vLLM.
- llama.cpp.
- torchao.
- ONNX Runtime.
- Device-specific optimization.
- Hybrid CPU/GPU inference.
- CPU/RAM/NVMe offloading.
- Model loading throughput.

Các định dạng như FP8, MXFP4 và NVFP4 hiện được hỗ trợ trong những hệ sinh thái serving/optimization phù hợp, nhưng tính hiệu quả phụ thuộc GPU và kernel. Đặc biệt, NVFP4 dùng block scaling, không đơn thuần là ép mọi số FP16 xuống bốn bit rồi chạy nhanh hơn.&#x20;

[image](https://www.google.com/s2/favicons?domain=https://docs.nvidia.com\&sz=32)

NVIDIA TensorRT

+1



## 17. GPU Computing, CUDA & Hardware-Aware AI

Mức độ: Working → Advanced

### 17.1. GPU Architecture

- CPU vs GPU execution.
- SMs và CUDA cores.
- Tensor Cores.
- GPU memory hierarchy.
- Registers.
- Shared memory.
- L1/L2 cache.
- Global memory.
- Memory bandwidth.
- Compute throughput.
- GPU utilization.

### 17.2. Parallel Programming

- Threads, blocks, grids.
- Warps.
- Thread synchronization.
- Memory coalescing.
- Occupancy.
- Register pressure.
- Warp divergence.
- Parallel reduction.
- Tiling.
- Kernel launch overhead.

### 17.3. CUDA Fundamentals

- CUDA runtime basics.
- Host vs device memory.
- Memory transfers.
- CUDA streams.
- Asynchronous execution.
- CUDA events.
- Kernel profiling.
- Synchronization.
- CUDA Graphs.
- Pinned memory.

### 17.4. High-Performance AI Kernels

- GEMM.
- Matrix tiling.
- Fused kernels.
- LayerNorm/RMSNorm kernels.
- Softmax kernels.
- Attention kernels.
- Quantized matrix multiplication.
- Kernel fusion.
- Triton language.
- CuTe/CUTLASS concepts.
- Custom PyTorch extensions.

### 17.5. Performance Profiling

- PyTorch Profiler.
- Nsight Systems.
- Nsight Compute.
- CPU vs GPU bottlenecks.
- Kernel launch overhead.
- Memory throughput.
- Arithmetic intensity.
- Roofline model.
- Operator-level profiling.
- End-to-end benchmarking.

### 17.6. CPU & Heterogeneous Inference

- NUMA basics.
- SIMD/vectorization.
- CPU inference.
- RAM bandwidth.
- CPU/GPU offloading.
- Pinned memory.
- Memory-mapped weights.
- SSD/NVMe model storage.
- PCIe transfer bottlenecks.
- Unified memory concepts.
- Heterogeneous scheduling.

## 18. Distributed Training & Large-Scale AI

Mức độ: Advanced • Working cho ML Platform Engineer

### 18.1. Distributed Computing Basics

- Processes vs workers.
- Distributed communication.
- Process groups.
- AllReduce.
- AllGather.
- ReduceScatter.
- Broadcast.
- Synchronization.
- Network topology.
- Communication overhead.

### 18.2. Distributed Training Strategies

- Data Parallelism.
- Distributed Data Parallel (DDP).
- Fully Sharded Data Parallel (FSDP).
- Tensor Parallelism.
- Pipeline Parallelism.
- Sequence Parallelism.
- Context Parallelism.
- Expert Parallelism.
- Hybrid Parallelism.

### 18.3. Memory-Efficient Distributed Training

- ZeRO Stage 1.
- ZeRO Stage 2.
- ZeRO Stage 3.
- Optimizer state sharding.
- Gradient sharding.
- Parameter sharding.
- Activation checkpointing.
- CPU/NVMe offloading.
- Mixed-precision distributed training.
- Distributed checkpointing.

### 18.4. Distributed Training Frameworks

- PyTorch Distributed.
- FSDP2.
- DeepSpeed.
- Megatron-LM.
- Hugging Face Accelerate.
- Ray Train.
- NCCL.
- DeviceMesh / DTensor.
- Multi-node launchers.

### 18.5. Large-Scale Training Challenges

- Stragglers.
- Network bottlenecks.
- Gradient synchronization.
- Fault tolerance.
- Failed-node recovery.
- Checkpoint consistency.
- Data pipeline bottlenecks.
- Compute-communication overlap.
- Hardware utilization.
- Training cost estimation.

PyTorch FSDP2 sử dụng cơ chế sharding dựa trên DTensor và tổ chức communication quanh các nhóm parameter, một chủ đề phù hợp để học sâu khi làm distributed training.&#x20;

[image](https://www.google.com/s2/favicons?domain=https://docs.pytorch.org\&sz=32)

PyTorch 2.14 documentation



# PHẦN V. PRODUCTION AI, MLOPS & INFRASTRUCTURE

## 19. MLOps & LLMOps

Mức độ: Core

### 19.1. ML Lifecycle Management

- Problem definition.
- Data collection.
- Data validation.
- Experimentation.
- Model training.
- Model evaluation.
- Model packaging.
- Deployment.
- Monitoring.
- Retraining.
- Retirement.

### 19.2. Experiment Tracking

- MLflow.
- Weights & Biases.
- TensorBoard.
- Experiment configurations.
- Hyperparameter logging.
- Metric logging.
- Artifact tracking.
- Run comparison.
- Reproducibility.
- Experiment lineage.

### 19.3. Model Registry

- Model versioning.
- Model artifacts.
- Model metadata.
- Staging vs production.
- Approval workflows.
- Model promotion.
- Rollback.
- Model cards.
- Reproducible builds.
- Artifact integrity.

### 19.4. Data & Pipeline Versioning

- DVC.
- LakeFS.
- Dataset snapshots.
- Pipeline versioning.
- Schema changes.
- Feature lineage.
- Reproducible data splits.
- Dataset-to-model traceability.

### 19.5. Pipeline Orchestration

- Airflow.
- Kubeflow Pipelines.
- Metaflow.
- Dagster.
- Prefect.
- Ray workflows.
- Scheduled training.
- Dependency management.
- Retry/recovery.
- Pipeline observability.

### 19.6. CI/CD/CT for AI

- Continuous Integration.
- Continuous Delivery.
- Continuous Training.
- Automated model validation.
- Data quality tests.
- Model regression checks.
- Artifact validation.
- Security scans.
- Deployment approval.
- Rollback strategies.

### 19.7. Monitoring & Drift

- Data drift.
- Concept drift.
- Prediction drift.
- Label distribution drift.
- Model quality degradation.
- Embedding distribution drift.
- Alert thresholds.
- Retraining triggers.
- Shadow evaluation.
- Performance by segment.

### 19.8. LLMOps-Specific Concerns

- Prompt versioning.
- Model provider/version tracking.
- Evaluation datasets.
- Tracing.
- Token usage.
- Cost dashboards.
- Agent tool traces.
- Prompt caching.
- Safety monitoring.
- Continuous LLM evaluation.
- Regression testing after model upgrades.

### 19.9. Feature Stores

- Offline feature store.
- Online feature store.
- Feature freshness.
- Point-in-time correctness.
- Training-serving skew.
- Real-time features.
- Feature materialization.
- Feature versioning.

## 20. Backend Engineering for AI Applications

Mức độ: Core

### 20.1. API Development

- FastAPI.
- Pydantic.
- REST API design.
- Request/response schemas.
- API documentation.
- HTTP status codes.
- Authentication middleware.
- Dependency injection.
- Health check endpoints.
- API versioning.

### 20.2. Asynchronous AI Backends

- Async/await.
- Async HTTP clients.
- Task queues.
- Background jobs.
- Streaming responses.
- Server-Sent Events.
- WebSockets.
- Cancellation.
- Timeout handling.
- Backpressure.
- Async exception handling.

### 20.3. API Reliability

- Retries.
- Exponential backoff.
- Jitter.
- Circuit breakers.
- Rate limiting.
- Idempotency keys.
- Request deduplication.
- Graceful degradation.
- Failover.
- Service health monitoring.

### 20.4. Database Integration

- PostgreSQL.
- Redis.
- Vector databases.
- Connection pooling.
- Transactions.
- Database migrations.
- Cache invalidation.
- Query optimization.
- Database access permissions.
- Multi-tenant schemas.

### 20.5. Messaging & Queue Systems

- Redis Queues.
- Celery.
- RabbitMQ.
- Kafka.
- Message delivery semantics.
- At-least-once processing.
- Idempotent consumers.
- Dead-letter queues.
- Retry handling.
- Job status tracking.

### 20.6. API Security

- API keys.
- OAuth 2.x concepts.
- OpenID Connect.
- JWT validation.
- RBAC và ABAC.
- Secret management.
- Rate-limit abuse prevention.
- Tenant isolation.
- Request validation.
- Audit logging.

### 20.7. AI-Specific Backend Design

- LLM gateway.
- Model routing.
- Provider fallbacks.
- Prompt template storage.
- Conversation persistence.
- Tool execution service.
- Usage metering.
- Streaming token handling.
- Per-user quota management.
- Async inference jobs.
- File upload and processing pipelines.

## 21. Docker, Kubernetes & Infrastructure

Mức độ: Core → Working

### 21.1. Docker

- Dockerfile.
- Images và containers.
- Volumes.
- Networking.
- Multi-stage builds.
- Docker Compose.
- Environment variables.
- GPU-enabled containers.
- Image size optimization.
- Security scanning.
- Container health checks.

### 21.2. Kubernetes

- Pods.
- Deployments.
- Services.
- ConfigMaps.
- Secrets.
- Persistent Volumes.
- Ingress.
- Resource requests/limits.
- Horizontal Pod Autoscaler.
- Cluster scheduling.
- Rolling updates.
- Jobs và CronJobs.

### 21.3. Kubernetes for AI

- GPU scheduling.
- GPU device plugins.
- NVIDIA GPU Operator.
- Model-serving deployments.
- Inference autoscaling.
- KServe.
- Ray Serve.
- GPU resource isolation.
- Multi-node inference.
- Multi-model deployments.

### 21.4. Infrastructure as Code

- Terraform.
- Helm.
- Kubernetes manifests.
- GitOps.
- Argo CD.
- Reproducible environments.
- Secrets separation.
- Infrastructure versioning.
- Environment drift.

### 21.5. Storage & Networking

- Object storage.
- Persistent volumes.
- High-throughput storage.
- Network latency.
- Load balancers.
- Internal service networking.
- TLS termination.
- Service discovery.
- GPU interconnect concepts.
- NVLink và InfiniBand (Advanced).

## 22. Cloud AI Engineering

Mức độ: Working

### 22.1. Cloud Fundamentals

- IaaS, PaaS, SaaS.
- Regions và availability zones.
- Compute instances.
- GPU instances.
- Object storage.
- Managed databases.
- IAM.
- Virtual private networks.
- Monitoring.
- Cost management.

### 22.2. AWS AI Stack

- S3.
- EC2 GPU.
- ECS/EKS.
- Lambda.
- SageMaker.
- Bedrock.
- IAM.
- CloudWatch.
- Managed data services.
- AWS deployment patterns.

### 22.3. Google Cloud AI Stack

- Cloud Storage.
- Compute Engine.
- Cloud Run.
- GKE.
- Vertex AI.
- BigQuery.
- IAM.
- Cloud Monitoring.
- Managed pipelines.

### 22.4. Microsoft Azure AI Stack

- Azure Blob Storage.
- Azure Virtual Machines.
- Azure Kubernetes Service.
- Azure Machine Learning.
- Azure AI Foundry.
- Azure-hosted model services.
- Azure AI Search.
- Azure Monitor.
- Identity and access management.

### 22.5. Cloud AI Deployment Strategies

- Managed API vs self-hosting.
- Serverless vs dedicated GPU.
- Spot/preemptible instances.
- Autoscaling.
- Multi-region availability.
- Network egress costs.
- GPU utilization.
- Model cold starts.
- Hybrid cloud/on-premises.
- Disaster recovery.

### 22.6. Cloud Cost Optimization

- GPU-hour cost.
- Token-based API pricing.
- Storage cost.
- Networking cost.
- Reserved/committed compute.
- Autoscaling economics.
- Cost attribution.
- Cost per inference.
- Cost per successful workflow.
- Cloud vs local TCO.

## 23. Production Architecture & AI System Design

Mức độ: Core → Working

### 23.1. System Design Fundamentals

- Functional requirements.
- Non-functional requirements.
- Scalability.
- Availability.
- Reliability.
- Maintainability.
- Throughput.
- Latency.
- Consistency.
- Fault tolerance.
- Cost constraints.

### 23.2. AI Application Architectures

- Monolithic AI service.
- Modular service architecture.
- Microservices.
- Event-driven AI systems.
- Batch inference.
- Online inference.
- Asynchronous inference.
- Streaming inference.
- Edge inference.
- Hybrid local/cloud AI systems.

### 23.3. Model Serving Architecture

- API gateway.
- Authentication layer.
- Routing layer.
- Inference workers.
- Model registry/storage.
- Caching layer.
- Observability pipeline.
- Autoscaling.
- Failure recovery.
- Rate limits.
- Admission control.

### 23.4. Model Routing & Cascades

- Small-model-first strategies.
- Complexity-based model routing.
- Confidence-based escalation.
- Cost-aware routing.
- Quality-aware routing.
- Multi-provider failover.
- Fallback chains.
- Ensemble inference.
- Cascaded inference.
- Routing evaluation.

### 23.5. Caching Strategies

- Response caching.
- Semantic caching.
- Embedding caching.
- Prompt caching.
- Prefix/KV caching.
- Retrieval caching.
- Cache invalidation.
- TTL policies.
- Privacy boundaries.
- Cache hit/miss metrics.

### 23.6. Scalability & High Availability

- Horizontal scaling.
- Vertical scaling.
- Load balancing.
- Replication.
- Sharding.
- Queue-based buffering.
- Backpressure.
- Request shedding.
- Multi-node inference.
- Blue-green deployments.
- Canary rollouts.
- Disaster recovery.

### 23.7. Capacity Planning

- Expected request rate.
- Concurrent users.
- Input/output token distributions.
- GPU memory requirements.
- Throughput benchmarks.
- Peak traffic.
- Queueing.
- Tail latency.
- Autoscaling thresholds.
- Capacity headroom.

### 23.8. Performance Engineering

- Profiling before optimizing.
- Bottleneck identification.
- Compute vs I/O bottlenecks.
- Serialization overhead.
- Network latency.
- CPU/GPU utilization.
- Memory efficiency.
- Caching trade-offs.
- Batch sizing.
- Cost/performance comparisons.

# PHẦN VI. AI SECURITY, SAFETY & GOVERNANCE

## 24. AI Security & Threat Modeling

Mức độ: Core

### 24.1. General Application Security

- Threat modeling.
- Authentication.
- Authorization.
- Least privilege.
- Secrets management.
- Encryption in transit.
- Encryption at rest.
- Network segmentation.
- Dependency scanning.
- Supply-chain security.
- Audit logs.
- Incident response.

### 24.2. LLM-Specific Security

- Prompt injection.
- Direct vs indirect prompt injection.
- Jailbreaking.
- System prompt leakage.
- Sensitive information disclosure.
- Insecure output handling.
- Data exfiltration.
- Training data poisoning.
- Retrieval poisoning.
- Model extraction.
- Denial-of-wallet attacks.

### 24.3. RAG Security

- Malicious retrieved documents.
- Hidden document instructions.
- Retrieval poisoning.
- Unauthorized document retrieval.
- Cross-tenant leakage.
- Index poisoning.
- Embedding-based attacks.
- Citation manipulation.
- Document provenance.
- Permission-aware retrieval.

### 24.4. Agent Security

- Agent goal hijacking.
- Tool misuse.
- Privilege escalation.
- Confused deputy problems.
- Unexpected code execution.
- Memory poisoning.
- Inter-agent communication attacks.
- Excessive agency.
- Unauthorized write actions.
- Cascading failures.
- Rogue agent behavior.

### 24.5. MCP Security

- Tool permission boundaries.
- Tool output trust.
- Server identity.
- OAuth scopes.
- Token audience validation.
- Tool poisoning.
- Malicious server descriptions.
- Credential leakage.
- Resource isolation.
- Approval gates.
- Sandbox boundaries.

### 24.6. Secure Agent Runtime

- Filesystem isolation.
- Network restrictions.
- Sandboxing.
- Credential scoping.
- Ephemeral credentials.
- Action allowlists.
- High-risk action confirmation.
- Resource quotas.
- Runtime monitoring.
- Emergency cancellation.
- Auditability.

### 24.7. AI Red Teaming

- Adversarial testing.
- Prompt injection benchmarks.
- Tool misuse scenarios.
- Permission boundary tests.
- Data exfiltration scenarios.
- Attack-path simulation.
- Red team datasets.
- Automated security evaluations.
- Security regression testing.
- Defensive mitigations.

Ở mốc 10/2026, cần cập nhật cả OWASP Top 10 for LLM Applications 2026 và OWASP Top 10 for Agentic Applications 2026. OWASP đã công bố bản LLM Top 10 mới trong tháng 9/2026 và có tổng kết các sự cố GenAI/Agentic AI được công bố ngày 08/10/2026.&#x20;

[image](https://www.google.com/s2/favicons?domain=https://genai.owasp.org\&sz=32)

OWASP Gen AI Security Project

+2



## 25. Responsible AI, Privacy & Compliance

Mức độ: Core → Working

### 25.1. Responsible AI Principles

- Fairness.
- Transparency.
- Explainability.
- Accountability.
- Robustness.
- Privacy.
- Safety.
- Human oversight.
- Reliability.
- Misuse prevention.

### 25.2. Privacy Engineering

- Personally Identifiable Information (PII).
- Data minimization.
- Consent.
- Data retention policies.
- Redaction.
- Anonymization.
- Pseudonymization.
- Access control.
- Data deletion workflows.
- Tenant isolation.

### 25.3. AI Governance

- Model cards.
- Dataset documentation.
- Risk assessments.
- Audit trails.
- Model version history.
- Human oversight procedures.
- Change management.
- Incident response documentation.
- Model decommissioning.
- AI system inventory.

### 25.4. Regulatory Awareness

- GDPR principles.
- EU AI Act và yêu cầu áp dụng theo từng trường hợp.
- Các quy định dữ liệu cá nhân tại Việt Nam.
- Data residency.
- Cross-border processing.
- Copyright and licensing.
- Sector-specific requirements.
- Contractual data-use restrictions.
- Evidence needed for compliance audits.

### 25.5. Fairness & Bias Evaluation

- Dataset representation.
- Demographic performance gaps.
- Sampling bias.
- Labeling bias.
- Fairness metrics.
- Disaggregated evaluation.
- Bias mitigation.
- Ongoing fairness monitoring.

### 25.6. Risk Management Frameworks

- NIST AI Risk Management Framework.
- NIST Generative AI Profile.
- ISO/IEC 42001 awareness.
- ISO/IEC 23894 awareness.
- Risk identification.
- Risk severity assessment.
- Control design.
- Verification and validation.
- Continuous risk monitoring.

NIST AI RMF là một nguồn tham chiếu tốt cho việc chuyển từ các nguyên tắc AI đáng tin cậy thành hoạt động đánh giá và kiểm soát có thể kiểm chứng.&#x20;

[image](https://www.google.com/s2/favicons?domain=https://airc.nist.gov\&sz=32)

AIRC



# PHẦN VII. ADVANCED AI SPECIALIZATIONS

Các phần tiếp theo là những nhánh chuyên môn. Một Middle AI Engineer nên có hiểu biết tổng quan nhưng thường chỉ cần đào sâu một hoặc hai nhánh phù hợp với công việc.

## 26. Multimodal AI & Generative Media

Mức độ: Working → Advanced

### 26.1. Multimodal Foundations

- Text, image, audio, video modalities.
- Cross-modal embeddings.
- Modality-specific encoders.
- Shared representation spaces.
- Cross-attention fusion.
- Early vs late fusion.
- Token-based multimodal modeling.
- Modality alignment.
- Multimodal datasets.
- Multimodal evaluation.

### 26.2. Vision-Language Models

- Image encoders.
- Visual tokenization.
- Vision projectors.
- Image-text alignment.
- Visual question answering.
- Image captioning.
- Object grounding.
- OCR-capable VLMs.
- Spatial reasoning.
- Multi-image context.
- High-resolution image processing.

### 26.3. Image Generation

- Diffusion fundamentals.
- Noise schedules.
- DDPM và DDIM.
- Classifier-free guidance.
- Latent Diffusion.
- Diffusion Transformers.
- Flow Matching.
- Rectified Flow.
- Text-to-image conditioning.
- Image-to-image generation.
- Inpainting.
- Outpainting.
- ControlNet.
- LoRA for image models.
- Generation quality metrics.

### 26.4. Video Generation

- Text-to-video.
- Image-to-video.
- Video-to-video.
- Temporal attention.
- Motion representations.
- Video latent spaces.
- Start/end-frame conditioning.
- Camera motion conditioning.
- Motion consistency.
- Character consistency.
- Temporal coherence.
- Video interpolation.
- Video upscaling.
- Frame rate and resolution trade-offs.
- Long-video generation from short clips.
- Video generation evaluation.

### 26.5. Advanced Audio Generation

- Neural vocoders.
- Acoustic models.
- Neural codecs.
- Audio tokenization.
- Voice cloning concepts.
- Speech-to-speech.
- Streaming TTS.
- Multilingual synthesis.
- Voice consistency.
- Audio generation evaluation.
- Latency optimization.

### 26.6. Real-Time Multimodal AI

- Streaming audio input.
- Streaming audio output.
- Turn-taking.
- Voice activity detection.
- Interruptions/barge-in.
- Audio-video synchronization.
- Real-time perception.
- Streaming multimodal inference.
- Real-time latency budgets.
- Jitter management.
- Conversation state synchronization.

### 26.7. Generative Media Pipelines

- Asset generation.
- Reference images.
- Character identity management.
- Shot planning.
- Keyframe generation.
- Batch generation.
- Upscaling.
- Quality control.
- Video/audio alignment.
- Editing workflows.
- Automated render pipelines.
- Human creative approval.

## 27. Recommender Systems, Graph ML & Causal AI

Mức độ: Working nếu làm ML sản phẩm • Advanced nếu chuyên sâu

### 27.1. Recommendation Systems

- Content-based filtering.
- Collaborative filtering.
- Matrix factorization.
- User-item embeddings.
- Two-tower models.
- Candidate generation.
- Retrieval stage.
- Ranking stage.
- Reranking.
- Learning-to-Rank.
- Cold-start problem.
- Exploration vs exploitation.

### 27.2. Recommendation Evaluation

- Precision\@K.
- Recall\@K.
- NDCG.
- MRR.
- Hit rate.
- Coverage.
- Diversity.
- Novelty.
- Offline vs online metrics.
- A/B testing recommender systems.

### 27.3. Graph Machine Learning

- Graph representations.
- Nodes, edges, attributes.
- Adjacency matrices.
- Graph embeddings.
- Node classification.
- Link prediction.
- Graph classification.
- Graph Convolutional Networks (GCN).
- GraphSAGE.
- Graph Attention Networks (GAT).
- Heterogeneous graphs.
- Knowledge graphs.

### 27.4. Graph Engineering

- Graph databases.
- Neo4j.
- PyTorch Geometric.
- DGL.
- Graph sampling.
- Neighbor sampling.
- Large-graph scalability.
- Graph feature stores.
- Graph inference.
- Graph-based recommendation.

### 27.5. Causal Inference

- Correlation vs causation.
- Confounding.
- Directed Acyclic Graphs (DAGs).
- Potential outcomes.
- Counterfactual reasoning.
- Propensity scores.
- Matching.
- Instrumental variables.
- Difference-in-Differences.
- Regression discontinuity.
- Uplift modeling.
- Treatment effect estimation.

### 27.6. Decision Intelligence

- Forecasting vs decision optimization.
- Experiment design.
- Causal impact.
- Business objective functions.
- Constraint optimization.
- Risk-aware decisions.
- Policy evaluation.
- Cost-benefit analysis.
- Human review in automated decisions.

## 28. Edge AI, On-Device AI & Efficient Deployment

Mức độ: Working → Advanced

### 28.1. Edge AI Fundamentals

- Cloud vs edge inference.
- On-device inference.
- Latency constraints.
- Privacy advantages.
- Offline operation.
- Power consumption.
- Thermal limits.
- Memory constraints.
- Hardware-specific acceleration.

### 28.2. Model Export & Interoperability

- ONNX.
- Torch export.
- ONNX Runtime.
- TensorRT engines.
- Core ML.
- TensorFlow Lite / LiteRT concepts.
- ExecuTorch.
- Graph optimization.
- Operator compatibility.
- Runtime validation.

### 28.3. Mobile & Embedded AI

- CPU inference.
- GPU inference.
- NPU accelerators.
- ARM architectures.
- Embedded Linux.
- Mobile memory constraints.
- Model compression.
- Quantized operators.
- Real-time inference.
- Power-aware scheduling.

### 28.4. Local AI Systems

- Running open-weight LLMs locally.
- CPU/GPU hybrid inference.
- Local embedding models.
- Local vector databases.
- Local RAG.
- Local agents.
- Offline speech processing.
- Local multimodal pipelines.
- Private model serving.
- Hardware capability detection.

### 28.5. Edge Optimization

- Model size reduction.
- Quantization.
- Distillation.
- Pruning.
- Operator fusion.
- Memory reuse.
- Batch-size optimization.
- Thread tuning.
- Hardware profiling.
- Accuracy-latency-power trade-offs.

## 29. Reinforcement Learning, Robotics & Embodied AI

Mức độ: Advanced • Chuyên môn tùy chọn

### 29.1. Reinforcement Learning

- Markov Decision Processes.
- States, actions, rewards.
- Discount factors.
- Value functions.
- Bellman equations.
- Policy iteration.
- Value iteration.
- Q-Learning.
- Deep Q Networks.
- Policy gradients.
- Actor-Critic.
- PPO.
- Offline RL.

### 29.2. Model-Based Learning

- Environment models.
- Dynamics prediction.
- Planning.
- Monte Carlo Tree Search.
- Model Predictive Control.
- World models.
- Latent dynamics.
- Simulation-based learning.

### 29.3. Robotics AI

- Robot perception.
- Localization.
- Mapping.
- SLAM fundamentals.
- Motion planning.
- Control systems basics.
- Imitation learning.
- Behavior cloning.
- Robot demonstrations.
- Sim-to-real transfer.
- Safety constraints.

### 29.4. Vision-Language-Action Models

- Vision-language-action architectures.
- Action tokenization.
- Action decoding.
- Language-conditioned policies.
- Visual observation processing.
- Robot action generation.
- Long-horizon tasks.
- Cross-robot generalization.
- Robotics datasets.
- Simulator evaluation.
- Embodied reasoning.

VLA là nhánh đang phát triển tích cực trong năm 2026, kết nối vision, language và hành động điều khiển. Đây là lĩnh vực chuyên sâu, không phải một chuẩn đầu vào bắt buộc cho mọi Middle AI Engineer.&#x20;

[image](https://www.google.com/s2/favicons?domain=https://ojs.aaai.org\&sz=32)

AAAI Publications

+1



# PHẦN VIII. FRONTIER TOPICS & AI RESEARCH LITERACY

## 30. Advanced & Emerging Topics in 2026

Mức độ: Awareness → Advanced

### 30.1. Advanced LLM Architectures

- Mixture of Experts.
- Expert routing.
- Load balancing losses.
- Sparse activation.
- State Space Models.
- Hybrid attention models.
- Linear attention.
- Long-context architectural optimizations.
- Subquadratic sequence modeling.
- Alternative decoding architectures.

### 30.2. Test-Time Compute & Reasoning

- Reasoning budgets.
- Test-time scaling.
- Best-of-N.
- Self-consistency.
- Verifier-guided search.
- Process reward models.
- Outcome reward models.
- Search over reasoning candidates.
- Adaptive compute allocation.
- Accuracy-cost trade-offs.

### 30.3. Advanced Inference Research

- Speculative decoding.
- EAGLE-style drafting.
- Learned draft models.
- Multi-token prediction heads.
- Sparse inference.
- KV Cache compression.
- Disaggregated serving.
- Heterogeneous inference.
- CPU/RAM/NVMe offloading.
- Emerging low-bit architectures.
- Inference-aware model design.

### 30.4. Ultra-Low-Bit Models

- Binary Neural Networks.
- 1-bit weight representations.
- Ternary weights.
- BitNet-style architectures.
- Quantization vs quantization-aware architecture design.
- Binary/ternary arithmetic.
- Low-bit accumulation.
- Specialized inference kernels.
- Accuracy/cost/performance trade-offs.

### 30.5. Advanced Post-Training

- Online reinforcement learning.
- Verifiable reward training.
- Reinforcement fine-tuning.
- Preference optimization variants.
- Self-generated training data.
- Synthetic data filtering.
- Distillation from reasoning models.
- Agent trajectory learning.
- Tool-use fine-tuning.
- Domain-specific post-training.

### 30.6. Next-Generation Agent Systems

- Long-horizon autonomous agents.
- Agent-to-agent delegation.
- Persistent agent memory.
- Memory consolidation.
- Automatic workflow planning.
- Environment-aware agents.
- Multi-agent coordination.
- Self-correction under objective evaluations.
- Agent execution sandboxes.
- Agent identity and permissions.
- Learned agent policies.

### 30.7. Advanced Generative Modeling

- Diffusion Transformers.
- Flow Matching.
- Rectified Flow.
- Few-step generation.
- Distilled diffusion models.
- Consistency models.
- Video generation architectures.
- World generation models.
- Spatially aware multimodal models.

### 30.8. Research Skills

- Reading arXiv papers critically.
- Identifying problem statements.
- Understanding experimental setups.
- Comparing baselines.
- Understanding ablation studies.
- Reproducing results.
- Checking dataset contamination.
- Reading benchmark leaderboards critically.
- Assessing implementation feasibility.
- Translating research into product experiments.

### 30.9. AI Research Reproducibility

- Reproducible environments.
- Dataset and checkpoint versioning.
- Exact hyperparameter logging.
- Re-running baselines.
- Statistical significance.
- Reproduction gaps.
- Ablation testing.
- Open-source code auditing.
- Measuring reported vs actual performance.

# PHẦN IX. ENGINEERING JUDGMENT & BUSINESS SKILLS

## 31. Problem Solving, System Ownership & Product Thinking

Mức độ: Core • Điểm phân biệt Middle với Junior

### 31.1. Problem Formulation

- Chuyển business problem thành ML task.
- Xác định input/output.
- Xác định success metrics.
- Xác định data availability.
- Xác định baseline.
- Xác định constraints.
- Chọn ML hay deterministic solution.
- Đánh giá feasibility trước khi train model.

### 31.2. Model Selection

- Classical ML vs Deep Learning.
- API models vs open-weight models.
- Small vs large models.
- Dense vs MoE.
- Fine-tuning vs RAG.
- Single agent vs multi-agent.
- Local vs cloud.
- Accuracy vs latency.
- Quality vs operating cost.
- Maintainability.

### 31.3. AI System Trade-Offs

- Quality.
- Latency.
- Throughput.
- Cost.
- Memory usage.
- Reliability.
- Security.
- Privacy.
- Scalability.
- Maintainability.
- Complexity.
- Time to market.

### 31.4. Experiment & Decision Discipline

- Baseline first.
- Hypothesis-driven experiments.
- Controlled comparisons.
- Ablation studies.
- Error analysis.
- Benchmark design.
- Statistical interpretation.
- Decision records.
- Stop/go criteria.
- Avoiding unnecessary complexity.

### 31.5. Production Ownership

- Monitoring ownership.
- Alert handling.
- Debugging incidents.
- Root-cause analysis.
- Writing postmortems.
- Rollback strategies.
- On-call collaboration.
- Capacity planning.
- Continuous improvements.
- Handling technical debt.

### 31.6. Team Engineering

- Writing technical documentation.
- Architecture Decision Records.
- Code review.
- Giving technical feedback.
- Reviewing pull requests.
- Designing API contracts.
- Working with Data Engineers.
- Working with Backend/DevOps.
- Collaborating with Product teams.
- Mentoring Junior engineers.

### 31.7. Business & Cost Awareness

- Business KPIs.
- ROI estimates.
- Unit economics.
- Cost per request.
- Cost per successful task.
- GPU utilization economics.
- API vs self-hosting TCO.
- Reliability costs.
- Data labeling costs.
- Ongoing maintenance costs.

### 31.8. Technical Communication

- Explaining model choices.
- Explaining failure modes.
- Communicating uncertainty.
- Presenting experiment results.
- Translating technical trade-offs.
- Communicating risks.
- Writing production readiness reviews.
- Defending architectural decisions.

# PHẦN X. MIDDLE AI ENGINEER COMPETENCY STANDARD

Sau 31 nhóm kiến thức, câu hỏi quan trọng nhất là: Đâu là ranh giới giữa Junior, Middle và Senior?

## 32. Yêu cầu năng lực thực tế

| Năng lực         | Junior                     | Middle                                           | Senior                                       |
| ---------------- | -------------------------- | ------------------------------------------------ | -------------------------------------------- |
| Mathematics & ML | Hiểu thuật toán            | Giải thích, lựa chọn và debug được               | Thiết kế phương pháp mới hoặc tối ưu sâu     |
| Deep Learning    | Train model theo hướng dẫn | Tự xây training pipeline, xử lý convergence      | Tối ưu training ở quy mô lớn                 |
| LLM              | Gọi API, viết prompt       | Xây ứng dụng LLM đáng tin cậy                    | Thiết kế nền tảng LLM quy mô lớn             |
| RAG              | Basic vector search        | Tối ưu retrieval, reranking, evaluation          | Thiết kế retrieval infrastructure quy mô lớn |
| Agentic AI       | Tool calling cơ bản        | Stateful workflow, recovery, tracing, eval       | Thiết kế distributed agent platform          |
| Quantization     | Biết INT8/INT4/FP8         | Chọn, quantize, benchmark và kiểm tra regression | Tối ưu kernel và thuật toán quantization     |
| MLOps            | Chạy notebook              | CI/CD, deployment, monitoring                    | Thiết kế ML platform                         |
| System Design    | Hiểu mô hình đơn giản      | Thiết kế hệ thống AI vừa và nhỏ                  | Thiết kế hệ thống lớn với nhiều trade-off    |
| Production       | Triển khai có hướng dẫn    | Tự xử lý phần lớn sự cố trong phạm vi sở hữu     | Dẫn dắt kiến trúc, reliability và team       |

## 33. Phân loại kỹ năng theo định hướng công việc

Chọn chuyên môn để xem trọng tâm cần học

AI Application / Agent Engineer

ML / Deep Learning Engineer

LLM Inference / Optimization Engineer

AI Platform / MLOps Engineer

Computer Vision / Multimodal Engineer

Phải thành thạo

Python, backend, API, LLM, prompting, RAG, agents, MCP, evals, security, LLMOps

Nên đào sâu

Context engineering, multi-agent systems, retrieval optimization, agent reliability

Chỉ cần biết tổng quan

CUDA kernels, distributed pretraining, robotics

## 34. Practical Capabilities: Middle phải thực sự làm được gì?

Đây là các năng lực đầu ra, không phải chỉ là những từ khóa xuất hiện trên CV.

## 0/20 năng lực

Checklist tự đánh giá

Đặt lại

1\. Core Engineering

Tự tổ chức một Python AI project có module, config, tests và CI.

Tự thiết kế data pipeline, validation và tránh data leakage.

Train, fine-tune và đánh giá model với baseline rõ ràng.

Debug NaN loss, OOM, gradient và các lỗi dữ liệu.

Xây API inference có authentication, logging và error handling.

2\. Modern AI

Xây RAG có hybrid retrieval, reranking, citations và evaluation.

Xây stateful AI agent với tool calling, retries và human approval.

Tạo golden datasets và tự động chạy regression evals.

Phân biệt khi nào dùng prompting, RAG, SFT, LoRA.

Tự tích hợp MCP server/client và bảo vệ tool permissions.

3\. Production & Optimization

Containerize và deploy AI service.

Đo P50/P95/P99 latency, throughput và cost.

Benchmark ít nhất hai phương án model hoặc serving engine.

Thực hiện quantization và đo quality regression.

Thiết lập monitoring, rollback và xử lý một sự cố production giả lập.

4\. Engineering Judgment

Giải thích trade-off giữa accuracy, latency, memory và cost.

Viết architecture diagram và deployment documentation.

Đưa ra quyết định bằng benchmark thay vì cảm giác.

Review code và giải thích nguyên nhân kỹ thuật của lựa chọn.

Chứng minh một feature hoạt động đúng trên những edge cases.

Đánh giá những phần tôi còn thiếu Checklist này chỉ là công cụ tự rà soát, không phải chứng nhận trình độ. Việc đánh giá Middle cần kiểm chứng bằng code, thiết kế và bài toán thực tế.

## 35. Thứ tự học hiệu quả

Không nên học tất cả đồng thời. Một thứ tự hợp lý để phát triển từ căn bản lên Middle AI Engineer tổng quát:

| Giai đoạn                 | Các topic ưu tiên | Kết quả cần đạt                                      |
| ------------------------- | ----------------- | ---------------------------------------------------- |
| 1. Foundation             | 1–4               | Hiểu Math, Python, SQL, Traditional ML               |
| 2. Deep Learning          | 5–8               | Tự train model bằng PyTorch, giải thích architecture |
| 3. LLM Engineering        | 9–11              | Xây LLM application, RAG, context engineering        |
| 4. Agentic AI             | 12–13             | Xây agent có state, tools, evaluation và tracing     |
| 5. Model Optimization     | 14–17             | Fine-tune, quantize, benchmark model inference       |
| 6. Production Engineering | 19–25             | Deployment, MLOps, system design, security           |
| 7. Specialization         | 18 và 26–30       | Chọn một hoặc hai nhánh chuyên sâu                   |
| 8. Engineering Ownership  | 31–34             | Tự làm chủ một hệ thống AI và giải thích quyết định  |

## 36. Năm dự án kiểm chứng năng lực

Nếu hoàn thành tốt các dự án dưới đây, bạn sẽ có bằng chứng thực tế mạnh hơn việc chỉ học lý thuyết hoặc sở hữu nhiều chứng chỉ.

| Dự án                           | Những gì phải triển khai                                                                                                     |
| ------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| 1. End-to-end ML System         | EDA → data validation → train nhiều models → hyperparameter tuning → evaluation → API → Docker → monitoring                  |
| 2. Production RAG               | Document ingestion → hybrid retrieval → reranking → grounded answers → golden eval set → user permissions → tracing          |
| 3. Autonomous Agent Workflow    | Planning → MCP/tools → state persistence → approval → error recovery → security → trajectory evaluation                      |
| 4. Optimized Local LLM Serving  | BF16 baseline → INT8/INT4/FP8 nếu phần cứng hỗ trợ → benchmark vLLM/llama.cpp → TTFT, TPOT, VRAM, cost và quality comparison |
| 5. Model Training & Fine-tuning | Dataset preparation → pretrained model → LoRA/SFT → evaluation → ablation → checkpoint management → serving                  |

## 37. Các nguồn chính thống nên theo dõi

Thay vì bám vào một danh sách tool cố định, các nguồn này hữu ích để cập nhật công nghệ và kiểm tra thay đổi về API, kiến trúc và giới hạn kỹ thuật.

| Lĩnh vực               | Nguồn                                                                                                |
| ---------------------- | ---------------------------------------------------------------------------------------------------- |
| Deep Learning          | [PyTorch Documentation](https://docs.pytorch.org/docs/stable/index.html)                             |
| LLM & Training         | [Hugging Face Documentation](https://huggingface.co/docs)                                            |
| Fine-tuning/RL         | [Hugging Face TRL](https://huggingface.co/docs/trl/index)                                            |
| LLM Serving            | [vLLM Documentation](https://docs.vllm.ai/en/stable/)                                                |
| LLM Evaluation         | [Evaluation Best Practices](https://developers.openai.com/api/docs/guides/evaluation-best-practices) |
| Agents                 | [OpenAI Agents SDK](https://developers.openai.com/api/docs/guides/agents/sdk)                        |
| MCP                    | [Model Context Protocol](https://modelcontextprotocol.io/)                                           |
| A2A                    | [Agent2Agent Protocol](https://a2a-protocol.org/latest/)                                             |
| Inference Optimization | [NVIDIA TensorRT](https://docs.nvidia.com/deeplearning/tensorrt/latest/)                             |
| AI Security            | [OWASP GenAI Security](https://genai.owasp.org/)                                                     |
| AI Risk Management     | [NIST AI Resource Center](https://airc.nist.gov/)                                                    |

## Kết luận

Nếu phải chọn các trụ cột quan trọng nhất cho một Middle AI Engineer trong tháng 10/2026, tôi sẽ chia thành:

Model Understanding

Hiểu ML/DL/Transformer, training, inference, evaluation và những giới hạn của mô hình.

AI Application Engineering

Xây RAG, agent workflows, tool integration và hệ thống có thể sử dụng thực tế.

Performance & Optimization

Hiểu latency, throughput, VRAM, quantization và cách đo chất lượng sau tối ưu.

Production Reliability

Deployment, MLOps, observability, security, testing và incident handling.

Engineering Judgment

Biết chọn giải pháp phù hợp, giải thích trade-offs, kiểm chứng bằng dữ liệu và tự chịu trách nhiệm về hệ thống.

Middle AI Engineer không nhất thiết phải biết tự viết CUDA kernel, train LLM hàng trăm tỷ parameters hay xây framework agent từ đầu. Nhưng phải biết cách đưa một giải pháp AI từ ý tưởng đến một hệ thống hoạt động ổn định, có đo lường, có khả năng debug và có thể giải thích tại sao chọn phương án đó.

Đó mới là thước đo quan trọng hơn số lượng framework đã học.
