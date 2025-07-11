  # Nhập Môn Xử Lý Ảnh Số - Lab 3
## Tiền xử lý ảnh: Làm mịn & Nâng cao chất lượng ảnh
** Sinh viên thực hiện:** Nguyễn Bùi Minh Đức MSSV: 2174802010856
Môn học: Nhập môn Xử lý ảnh số
Giảng viên: Đỗ Hữu Quân

## Mục tiêu: 
Thực hành các kỹ thuật xử lý hình học như cắt ảnh, tịnh tiến, xoay, thay đổi kích thước, biến dạng ảnh... sử dụng ngôn ngữ Python và thư viện xử lý ảnh số.

## Ý nghĩa:
Giúp hiểu và áp dụng các phép biến đổi hình học cơ bản để chuẩn hóa và xử lý ảnh phục vụ các bài toán thị giác máy tính.

## Công nghệ sử dụng

Python: Ngôn ngữ chính
numpy: xử lý ma trận
matplotlib.pylab: hiển thị ảnh
imageio.v2: đọc/ghi ảnh
scipy.ndimage: các phép biến đổi hình học nâng cao

## Các kỹ thuật xử lý ảnh thực hiện
### 1. Chọn đối tượng trong ảnh
Mục đích: Lấy vùng quan tâm từ ảnh gốc.
** 
** data = iio.imread('fruit.jpg')
** bmg = data[800:1200,  570:980]


### 2. Tịnh tiến đơn
Mục đích: Di chuyển toàn bộ nội dung ảnh theo một vector dịch.
** 
** data = iio.imread('fruit.jpg', mode='F')
** bdata = nd.shift(data, (100, 25))


###  3. Thay đổi kích thước ảnh
Mục đích: Phóng to hoặc thu nhỏ ảnh.
** 
** from scipy import ndimage
** data = iio.imread('fruit.jpg', mode='F')
** bdata = ndimage.zoom(data, 0.5)


###  4. Xoay ảnh
Mục đích: Xoay ảnh quanh tâm ảnh.
** 
** data = iio.imread('fruit.jpg', mode='F')
** bdata = ndimage.rotate(data, 45)

###  5. Dilation và Erosion
Mục đích:
Dilation: làm giãn các vùng sáng.
Erosion: làm mòn, thu nhỏ vùng sáng.
** 
** from scipy import ndimage
** img = iio.imread('fruit.jpg')
** dilated = ndimage.grey_dilation(img, size=(10,10,1))
** eroded = ndimage.grey_erosion(img, size=(10,10,1))

###  6. Coordinate Mapping
Mục đích: Thực hiện biến dạng ảnh theo ánh xạ vị trí điểm ảnh.
** 
** def mapping_func(output_coords):
**     x, y = output_coords
**     return (x, y + 30 * np.sin(x / 20))

** img = iio.imread('fruit.jpg')
** mapped = ndimage.geometric_transform(img, mapping_func)


###  7. Biến đổi chung (Generic Transformation)
Mục đích: Áp dụng phép biến đổi affine tổng quát cho ảnh.
** 
** data = iio.imread('fruit.jpg')
** matrix = [[1, -0.5], [0.5, 1]]
** offset = (0, 0)
** bdata = ndimage.affine_transform(data, matrix, offset=offset)


