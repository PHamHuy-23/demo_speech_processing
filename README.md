# Dự án Mô hình Xử lý Tiếng nói (Speech Processing)

Dự án này triển khai các mô hình học sâu (Deep Learning) để thực hiện bài toán nhận dạng từ khóa (Keyword Spotting) trong âm thanh. 

## Về Mô hình
Các kiến trúc mô hình trong dự án được thiết kế để trích xuất đặc trưng từ file âm thanh và phân loại thành các lệnh giọng nói hoặc từ khóa cụ thể. Quá trình huấn luyện, đánh giá và tinh chỉnh mô hình được thể hiện chi tiết qua các notebook và mã nguồn đi kèm.

## Cách chạy Demo dự án

### 1. Kích hoạt môi trường
Dự án đã có sẵn môi trường ảo (`.venv`). Hãy kích hoạt nó trước khi chạy code:
```bash
# Trên Windows
.venv\Scripts\activate
```

### 2. Chạy file Demo / Huấn luyện
Để xem demo quá trình huấn luyện và kết quả của mô hình, bạn có thể chạy file Jupyter Notebook:

1. Mở file **`Kaggle_Honk_Training.ipynb`** bằng VS Code, Jupyter Notebook hoặc môi trường Kaggle.
2. Chạy lần lượt các cell từ trên xuống dưới để load dữ liệu, khởi tạo mô hình và xem output demo.

*(Lưu ý: Nếu bạn có file script Python riêng để chạy inference nhận diện mẫu âm thanh trực tiếp, bạn có thể chạy thông qua lệnh như `python script_ten_file.py` trong terminal)*
