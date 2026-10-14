# Notebook-first learning

Mỗi topic có `notebooks/README.md` để đăng ký notebook nội bộ và liên kết bên ngoài.

## Notebook trong repository

- Lưu tại `knowledge/<part>/<module>/<topic>/notebooks/<descriptive-name>.ipynb`.
- Giữ code chia thành nhiều cell có ý nghĩa: mục tiêu → setup → thí nghiệm → kết quả → phân tích.
- **Chạy notebook và Save trước khi commit** để outputs nằm trong .ipynb và có thể xem được trên GitHub khi trình xem hỗ trợ.
- Ghi phiên bản Python, PyTorch/CUDA, phần cứng, seeds, môi trường và dữ liệu đầu vào phù hợp; với benchmark, ghi warmup, synchronization và cách đo.
- Không commit secrets, token, thông tin định danh cá nhân, tập dữ liệu/weights cỡ lớn hoặc output vô tình chứa bí mật.
- Với notebook output quá lớn hoặc widget không hiện tốt trên GitHub, cung cấp thêm bản tóm tắt kết quả/ảnh minh họa hoặc link nbviewer.

## Notebook ngoài repository

Có thể liên kết Google Colab, Kaggle Notebook hoặc GitHub notebook từ repo khác tại `notebooks/README.md`; thêm URL đầy đủ, quyền truy cập cần thiết và thông tin outputs có sẵn hay không.

## Quy tắc

Không đánh dấu L3 chỉ vì một notebook chạy được: bài thực hành cần được người học giải thích và thực hiện độc lập.
