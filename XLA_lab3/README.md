              ## Nhập Môn Xử Lý Ảnh Số - Lab 3
Tiền xử lý ảnh: Làm mịn & Nâng cao chất lượng ảnh
Sinh viên thực hiện: Nguyễn Bùi Minh Đức MSSV: 2174802010856
Môn học: Nhập môn Xử lý ảnh số
Giảng viên: Đỗ Hữu Quân

Mục tiêu: 
Thực hành các kỹ thuật xử lý hình học như cắt ảnh, tịnh tiến, xoay, thay đổi kích thước, biến dạng ảnh... sử dụng ngôn ngữ Python và thư viện xử lý ảnh số.

Ý nghĩa:
Giúp hiểu và áp dụng các phép biến đổi hình học cơ bản để chuẩn hóa và xử lý ảnh phục vụ các bài toán thị giác máy tính.

Công nghệ sử dụng

Python: Ngôn ngữ chính
numpy: xử lý ma trận
matplotlib.pylab: hiển thị ảnh
imageio.v2: đọc/ghi ảnh
scipy.ndimage: các phép biến đổi hình học nâng cao

Các kỹ thuật xử lý ảnh thực hiện
1.Chọn đối tượng trong ảnh
Mục đích: Lấy vùng quan tâm từ ảnh gốc.

data = iio.imread('fruit.jpg')
bmg = data[800:1200,  570:980]
iio.imsave('orange.jpg', bmg)
plt.imshow(bmg)
plt.show()
