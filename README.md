# Dự án Mô hình Xử lý Tiếng nói (Speech Processing)

Dự án này triển khai các mô hình học sâu (Deep Learning) để thực hiện bài toán nhận dạng từ khóa (Keyword Spotting) trong âm thanh. Mã nguồn ban đầu dựa trên mô hình Honk (PyTorch).

## 1. Hướng dẫn Clone dự án

Để tải dự án này về máy của bạn, hãy mở Terminal (hoặc Command Prompt / PowerShell) và chạy các lệnh sau:

```bash
# Clone kho lưu trữ về máy
git clone https://github.com/PHamHuy-23/demo_speech_processing.git

# Di chuyển vào thư mục dự án
cd demo_speech_processing
```

## 2. Hướng dẫn sử dụng Mô hình Huấn luyện sẵn (Pre-trained Models)

Dự án đã đính kèm sẵn các file dữ liệu mô hình đã được huấn luyện thành công (bao gồm `model.pt`, `res8.pt`, `google-speech-dataset.pt`,...) nằm trong thư mục **`honk/model/`**. 

Người dùng **không cần phải huấn luyện lại từ đầu** mà có thể dùng trực tiếp các file mô hình này để kiểm tra và nhận diện giọng nói.

### Kích hoạt môi trường chạy
Dự án yêu cầu cài đặt Python. Nếu bạn đang chạy trực tiếp từ mã nguồn đã tải, hãy kích hoạt môi trường ảo:
```bash
# Trên Windows
.venv\Scripts\activate
```

### Chạy Server & Giao diện Demo
1. **Chạy Server Backend:** Server sẽ tự động nạp các file mô hình `.pt` trong thư mục `honk/model/` để phân tích âm thanh.
   ```bash
   python honk/__main__.py
   ```
   *(Server mặc định chạy tại địa chỉ `http://127.0.0.1:16888`)*

2. **Chạy Giao diện UI (Tkinter):** Mở **thêm một terminal khác** (cũng nhớ kích hoạt `.venv`) và chạy:
   ```bash
   python honk/utils/speech_demo_tk.py
   ```
   Giao diện sẽ hiện lên, tự động thu âm từ microphone và bôi màu xanh lá cây vào các từ khóa (như *yes, no, up, down...*) khi mô hình nhận diện thành công giọng nói của bạn.

## 3. Hướng dẫn xem / chạy Notebook Training (trên Kaggle)

Nếu bạn muốn xem toàn bộ quy trình, kiến trúc mạng CNN, hoặc muốn tự tay huấn luyện (training) lại mô hình, dự án có đi kèm file **`Kaggle_Honk_Training.ipynb`**.

**Đặc điểm nổi bật:**
- Notebook này đã được **chỉnh sửa, sửa lỗi và tối ưu hóa để chạy thành công 100% trên nền tảng Kaggle** với cấu hình GPU mạnh.
- Nó xử lý toàn bộ quá trình từ tải dataset, khởi tạo model (Res8, Res15...), huấn luyện và lưu ra trọng số (`.pt`).

**Cách chạy Notebook trên Kaggle:**
1. Đăng nhập vào [Kaggle](https://www.kaggle.com/) và tạo một Notebook mới.
2. Chọn `File -> Import Notebook` và tải lên file `Kaggle_Honk_Training.ipynb` từ thư mục dự án của bạn.
3. Trong menu bên phải (Settings), bật tính năng GPU (Accelerator -> GPU T4x2 hoặc P100).
4. Chạy toàn bộ các cell (`Run All`) để xem quá trình đào tạo mô hình diễn ra.
