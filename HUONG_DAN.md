# 📖 Hướng Dẫn Sử Dụng & Kết Quả Trực Quan Hóa Dữ Liệu

Chào mừng bạn đến với tài liệu hướng dẫn thực thi và diễn giải kết quả cho bài tập trực quan hóa dữ liệu khí hậu & thủy văn đa chiều.

---

## 🛠️ 1. Hướng Dẫn Cài Đặt & Chạy Script

### Bước 1: Cài đặt các thư viện cần thiết
Dự án sử dụng ngôn ngữ Python 3 cùng các thư viện phân tích và trực quan hóa dữ liệu phổ biến. Bạn có thể cài đặt nhanh chóng bằng lệnh sau trong terminal/command prompt:

```bash
pip install pandas matplotlib seaborn numpy
```

### Bước 2: Thực thi script
Chạy lệnh sau từ thư mục gốc của dự án (`multi-dimensional-data-visualization`):

- **Trên Windows**:
  ```bash
  py src/create_visualizations.py
  ```
  *(hoặc `python src/create_visualizations.py`)*

- **Trên macOS / Linux**:
  ```bash
  python3 src/create_visualizations.py
  ```

---

## 📊 2. Kết Quả Đầu Ra Mong Đợi (Expected Results)

Khi chạy thành công, script sẽ đọc dữ liệu từ thư mục `data/`, xử lý và xuất ra 4 tệp hình ảnh biểu đồ sắc nét (độ phân giải `300 dpi`) lưu trong thư mục `output/`:

```text
Generated figures:
- output/weather_heatmap.png        # Bản đồ nhiệt thời tiết theo thành phố
- output/weather_scatter.png        # Biểu đồ phân tán đa chiều thời tiết hàng ngày
- output/global_temp_heatmap.png    # Bản đồ nhiệt dị thường nhiệt độ toàn cầu
- output/minnesota_precip_line.png  # Biểu đồ đường lượng mưa tại Minnesota
```

---

## 📈 3. Chi Tiết Các Biểu Đồ & Diễn Giải Kết Quả

### 1. Bản đồ nhiệt nhiệt độ trung bình hàng tháng (`weather_heatmap.png`)
* **Mô tả**: Biểu đồ hiển thị nhiệt độ trung bình (°F) theo từng tháng (cột từ 1-12) cho các thành phố như Auckland, Beijing, Chicago, Mumbai, và San Diego.
* **Quy luật rút ra**:
  - **Mumbai**: Nhiệt độ luôn cao và ổn định (trên 75°F quanh năm).
  - **Beijing & Chicago**: Có sự dao động mùa cực kỳ lớn (mùa đông lạnh sát mức đóng băng ~30-40°F, mùa hè nóng ẩm ~70-80°F).
  - **Auckland & San Diego**: Khí hậu ôn hòa ôn đới rất ổn định, không có biến động nhiệt độ quá gắt giữa các mùa.

### 2. Biểu đồ phân tán tích hợp đa chiều thời tiết hàng ngày (`weather_scatter.png`)
* **Mô tả**: Mỗi điểm tròn đại diện cho 1 ngày quan trắc. Trục X thể hiện độ ẩm tương đối (%), trục Y thể hiện nhiệt độ (°F), màu sắc phân biệt các thành phố và kích thước chấm thể hiện lượng mưa (precip).
* **Quy luật rút ra**:
  - Những ngày mưa lớn tập trung ở vùng có độ ẩm trung bình đến cao.
  - Mumbai chiếm các điểm ở góc trên bên phải (vừa nóng vừa có độ ẩm cao).
  - Auckland ôn hòa với độ ẩm cao, trong khi Beijing và Chicago trải dài rộng khắp dải nhiệt độ tùy theo mùa.

### 3. Bản đồ nhiệt dị thường nhiệt độ toàn cầu từ năm 1880–2025 (`global_temp_heatmap.png`)
* **Mô tả**: Bản đồ nhiệt mật độ cao thể hiện sự chênh lệch nhiệt độ đất liền và đại dương so với mốc trung bình giai đoạn 1951-1980.
* **Quy luật rút ra**:
  - **Màu xanh lam (lạnh hơn)** áp đảo hoàn toàn giai đoạn lịch sử từ 1880 đến những năm 1930.
  - Từ những năm 1980 trở đi, bản đồ chuyển dịch hoàn toàn sang **màu đỏ đậm (ấm hơn)**.
  - Đặc biệt thập kỷ qua (2015-2025) ghi nhận những đợt dị thường nhiệt độ cao kỷ lục, minh chứng rõ ràng cho hiện tượng nóng lên toàn cầu.

### 4. Biểu đồ đường lượng mưa hàng tháng tại Minnesota (`minnesota_precip_line.png`)
* **Mô tả**: Biểu đồ đường thể hiện diễn biến lượng mưa (inches) tại 6 địa điểm nông nghiệp ở Minnesota trong suốt một thập kỷ (1927-1936).
* **Quy luật rút ra**:
  - Lượng mưa mang tính chu kỳ mùa rất rõ rệt, luôn đạt đỉnh vào các tháng mùa hè (tháng 6 đến tháng 8) và xuống thấp nhất vào mùa đông.
  - Địa điểm **Waseca** và **St. Paul** ghi nhận tổng lượng mưa cao hơn hẳn so với **Morris** hay **Crookston**.
  - Khoảng trống đứt gãy trên đường biểu diễn của Duluth vào cuối năm 1931 thể hiện việc thiếu dữ liệu ghi nhận tại thời điểm đó.
