# Dự án Mô hình Xử lý Tiếng nói (Speech Processing)

Dự án này triển khai các mô hình học sâu (Deep Learning) để thực hiện bài toán nhận dạng từ khóa (Keyword Spotting) trong âm thanh. 

## Về Mô hình
Các kiến trúc mô hình trong dự án được thiết kế để trích xuất đặc trưng từ file âm thanh và phân loại thành các lệnh giọng nói hoặc từ khóa cụ thể. Quá trình huấn luyện, đánh giá và tinh chỉnh mô hình được thể hiện chi tiết qua các notebook và mã nguồn đi kèm.

## Hướng dẫn chạy Dự án (Server & Giao diện Demo)

Dự án bao gồm một **Server API** để xử lý mô hình và một **Giao diện (UI)** viết bằng Tkinter, cho phép thu âm trực tiếp qua microphone và hiển thị kết quả nhận diện.

### 1. Kích hoạt môi trường
Dự án đã có sẵn môi trường ảo (`.venv`). Khởi động môi trường này trước khi chạy code:
```bash
# Trên Windows
.venv\Scripts\activate
```

### 2. Chạy Server (Backend)
Server sẽ tải mô hình và lắng nghe các request âm thanh gửi tới. 
Mở một terminal, kích hoạt `.venv` và chạy lệnh sau:
```bash
python honk/__main__.py
```
*(Lưu ý: Mặc định Server sẽ chạy ở địa chỉ `http://127.0.0.1:16888`)*

### 3. Chạy Giao diện Demo (UI)
Sau khi Server đã chạy thành công, hãy mở **thêm một terminal khác** (cũng kích hoạt `.venv`), chạy script giao diện:
```bash
python honk/utils/speech_demo_tk.py
```
**Cách sử dụng:** 
- Một cửa sổ giao diện sẽ hiện lên với danh sách các từ khóa dự án hỗ trợ (như *yes, no, up, down, stop, go...*).
- Chương trình sẽ tự động thu âm từ microphone của bạn và gửi đến Server liên tục.
- Bất cứ khi nào bạn đọc một từ khóa và mô hình nhận dạng được, từ đó trên màn hình giao diện sẽ được **nhấn sáng màu xanh lá cây**.

---
**Tham khảo:** Để xem chi tiết quá trình cấu hình, huấn luyện từ đầu và kết quả đánh giá của mô hình, bạn có thể mở và chạy file `Kaggle_Honk_Training.ipynb`.
