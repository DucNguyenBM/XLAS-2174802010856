# Nhập Môn Xử Lý Ảnh Số - Lab 4  
## Phân Vùng Ảnh & Biến Đổi Đối Tượng

**Sinh viên thực hiện:** Nguyễn Bùi Minh Đức  
**MSSV:** 2174802010856  
**Môn học:** Nhập môn Xử lý ảnh số  
**Giảng viên:** Đỗ Hữu Quân  

---

## 1. Mục tiêu

- Thực hiện phân vùng ảnh bằng kỹ thuật ngưỡng hóa (thresholding) và phân vùng theo vùng.
- Sử dụng các phép biến đổi hình thái học trên ảnh nhị phân.
- So sánh sự khác biệt giữa các phương pháp phân vùng và biến đổi ảnh.

---

## 2. Nội dung thực hành

### 2.1 Phân vùng theo Histogram

#### 2.1.1 Phương pháp Otsu

- Tự động xác định ngưỡng tối ưu để phân tách ảnh xám thành vùng nền và vùng đối tượng.
- Kỹ thuật này tối ưu phương sai giữa các lớp.

#### 2.1.2 Phương pháp Adaptive Thresholding

- Áp dụng phương pháp `threshold_local` với cửa sổ cục bộ để phân ngưỡng ảnh.
- Phù hợp khi ảnh có ánh sáng không đồng đều.

---

### 2.2 Phân vùng theo Region

- Thực hiện các bước:
  - Chuyển ảnh màu sang ảnh xám.
  - Ngưỡng hóa ảnh bằng phương pháp Otsu kết hợp nhị phân nghịch đảo.
  - Áp dụng phép xói mòn để giảm nhiễu.
  - Sử dụng `distanceTransform` để tính khoảng cách từ nền đến đối tượng.
  - Ngưỡng hóa ảnh khoảng cách để xác định vùng chắc chắn là đối tượng.
  - Gán nhãn các vùng ảnh và áp dụng thuật toán `watershed` để phân vùng chi tiết hơn.

---

### 2.3 Biến đổi đối tượng trong ảnh

#### 2.3.1 Sử dụng `binary_dilation`

- Phép dãn nở mở rộng vùng đối tượng trắng trong ảnh nhị phân.
- Giúp kết nối các vùng gần nhau.

#### 2.3.2 Sử dụng `binary_opening`

- Phép mở ảnh: co lại sau đó dãn nở.
- Loại bỏ nhiễu nhỏ và giữ lại các vùng lớn.

#### 2.3.3 Sử dụng `binary_erosion`

- Phép co lại ảnh làm nhỏ vùng đối tượng trắng.
- Tách rời các đối tượng dính liền.

#### 2.3.4 Sử dụng `binary_closing`

- Phép đóng ảnh: dãn nở sau đó co lại.
- Làm đầy các lỗ nhỏ và làm mịn biên đối tượng.

---

## 3. Kết luận

- Các phương pháp ngưỡng hóa như Otsu và adaptive thresholding giúp phân vùng ảnh hiệu quả tùy theo điều kiện chiếu sáng.
- Phân vùng theo vùng sử dụng watershed mang lại kết quả tốt hơn trong việc tách các đối tượng gần nhau.
- Các phép biến đổi hình thái học là công cụ mạnh mẽ để xử lý ảnh nhị phân, phục vụ nhiều bài toán nhận dạng, phân đoạn trong thị giác máy tính.
