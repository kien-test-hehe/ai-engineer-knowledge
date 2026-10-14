# Quy trình quản lý kiến thức

1. Chọn topic theo ID trong `indexes/topics.json`.
2. Đọc đúng thư mục topic + dependencies, không tải toàn bộ repo vào context.
3. Học và kiểm chứng trước khi lưu tài liệu.
4. Viết nội dung mới trên branch riêng, tạo Pull Request (PR) để người học xem diff.
5. Không merge vào `main` khi người học chưa đồng ý.
6. Chỉ nâng `mastery` sau khi có bài kiểm tra/chứng cứ rõ ràng; không tự nâng vì AI đã giảng.
7. Sau khi notebook được thêm, cập nhật `notebooks/README.md` và lưu outputs đã chạy, không commit dữ liệu nhạy cảm.
8. Khi kiến thức thay đổi theo phiên bản công cụ, giữ nguồn, version, điều kiện benchmark và thay đổi có kiểm chứng.

**Những gì được tạo trong commit scaffold:** thư mục, mục lục, mục tiêu syllabus, template và registry; **không phải** ghi chú chuyên môn đã được duyệt.
