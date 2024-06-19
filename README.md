•	Họ và Tên: Nguyễn Chí Phát

•	MSSV: K215480106116

•	Lớp: K57KMT

•	Môn học: Hệ quản trị cơ sở dữ liệu

---------------------------------------------------------
# CHƯƠNG TRÌNH QUẢN LÝ BÁN HÀNG CỦA CỬA HÀNG MÁY TÍNH
Mô tả bài toán quản lý : Bài tập sử dụng ngôn ngữ truy vấn SQL để quản lý việc nhập xuất hàng cũng như việc buôn bán kinh doanh của cửa hàng máy tính .

##  NHỮNG CHỨC NĂNG XÂY DỰNG ĐỂ QUẢN LÝ BÁN HÀNG CỦA CỬA HÀNG MÁY TÍNH 
1.Quản lý người dùng :
  - Đăng nhập , liệt kê tổng số người dùng
  - Thêm , Sửa , Xóa thông tin người dùng
  - Đổi mật khẩu , kiểm tra đăng nhập người dùng.
    
2.Quản lý hàng hóa :
  - Liệt kê hàng hóa
  - Thêm , Sửa , Xóa hàng hóa.
    
3.Quản lý bán hàng :
  - Thêm , sửa , xóa hóa đơn
   - Thêm chi tiết hóa đơn , Cập nhật số lượng chi tiết hóa đơn, xóa chi tiết hóa đơn.
     
## BÁO CÁO 
 - Báo cáo số lượng mặt hàng còn tồn đọng trong kho
 - Báo cáo mặt hàng bán chạy nhất trong tháng
## Các bảng của hệ thống 
1.KhachHang(#MaKhachHang, TenKhachHang, Email, SoDienThoai, DiaChi)

2.NhaCungCap(#MaNhaCungCap, TenNhaCungCap, NguoiLienHe, DiaChi, ThanhPho, QuocGia, SoDienThoai)

3.SanPham(#MaSanPham, TenSanPham, MaNhaCungCap, GiaDonVi, SoLuongTonKho)

4.DonHang(#MaDonHang, MaKhachHang, NgayDatHang, GiaTri)

5.ChiTietDonHang(#MaChiTietDonHang, MaDonHang, MaSanPham, SoLuong, GiaDonVi)

6.KhoHang(#MaKhoHang, MaSanPham, SoLuongTon)

### Mô tả các bảng

1.KhachHang: lưu thông tin khách hàng

    -MaKhachHang: khoá chính, kiểu INT
  
    -TenKhachHang: kiểu NVARCHAR(100)
  
    -Email: kiểu NVARCHAR(100)
  
    -SoDienThoai: kiểu NVARCHAR(20)
  
    -DiaChi: kiểu NVARCHAR(255)

2.NhaCungCap: lưu thông tin nhà cung cấp

    -MaNhaCungCap: khoá chính, kiểu INT

    -TenNhaCungCap: kiểu NVARCHAR(100)

    -NguoiLienHe: kiểu NVARCHAR(100)

    -DiaChi: kiểu NVARCHAR(255)
  
    -ThanhPho: kiểu NVARCHAR(50)

    -QuocGia: kiểu NVARCHAR(50)

    -SoDienThoai: kiểu NVARCHAR(20)

3.SanPham: lưu thông tin sản phẩm

    -MaSanPham: khoá chính, kiểu INT

    -TenSanPham: kiểu NVARCHAR(100)

    -MaNhaCungCap: khoá ngoại, kiểu INT

    -GiaDonVi: kiểu DECIMAL(10, 2)

    -SoLuongTonKho: kiểu INT

  4.DonHang: lưu thông tin đơn hàng

    -MaDonHang: khoá chính, kiểu INT

    -MaKhachHang: khoá ngoại, kiểu INT

    -NgayDatHang: kiểu DATE

    -GiaTri: kiểu DECIMAL(10, 2)

  5.ChiTietDonHang: lưu thông tin chi tiết đơn hàng

    -MaChiTietDonHang: khoá chính, kiểu INT

    -MaDonHang: khoá ngoại, kiểu INT

    -MaSanPham: khoá ngoại, kiểu INT

    -SoLuong: kiểu INT

    -GiaDonVi: kiểu DECIMAL(10, 2)

  6.KhoHang: lưu thông tin kho hàng
  
    -MaKhoHang: khoá chính, kiểu INT

    -MaSanPham: khoá ngoại, kiểu INT

    -SoLuongTon: kiểu INT

  *Tạo các bảng đã mô tả trong Sql sever :
  1.Bảng Khách hàng 

  ![image](https://github.com/PhatKuriKaraDivincarnate/B-i-t-p-l-n-HQTCSDL/assets/168658766/0ea86d97-6672-4544-8bff-76a8296c758f)

  2.Bảng Nhà cung cấp 

  ![image](https://github.com/PhatKuriKaraDivincarnate/B-i-t-p-l-n-HQTCSDL/assets/168658766/d520b8d6-29a6-4135-9631-e7a80e8f2cc9)

  3.Bảng Sản phẩm 

  ![image](https://github.com/PhatKuriKaraDivincarnate/B-i-t-p-l-n-HQTCSDL/assets/168658766/2c5319d7-e8a0-4714-8ae2-98d04a0ea2ff)

  4.Bảng đơn hàng 

  ![image](https://github.com/PhatKuriKaraDivincarnate/B-i-t-p-l-n-HQTCSDL/assets/168658766/f5c26591-1415-46e7-819e-572cdfaf87f1)

  5.Bảng Chi tiết đơn hàng 

  ![image](https://github.com/PhatKuriKaraDivincarnate/B-i-t-p-l-n-HQTCSDL/assets/168658766/8a4e618d-0b13-4def-8417-219045ab80e8)

  6.Bảng kho hàng

  ![image](https://github.com/PhatKuriKaraDivincarnate/B-i-t-p-l-n-HQTCSDL/assets/168658766/168b2775-b818-435e-8a58-3ec044af64ee)

  ## CÁC CHỨC NĂNG 

  1.Xem tất cả các đơn hàng và chi tiết đơn hàng 

  ![image](https://github.com/PhatKuriKaraDivincarnate/B-i-t-p-l-n-HQTCSDL/assets/168658766/3d4a16e4-ca84-4069-a54e-6383f1f0ee36)

  2.Quản lý người dùng ( Thêm , sửa , xóa thông tin người dùng theo các action lựa chọn )

  ![image](https://github.com/PhatKuriKaraDivincarnate/B-i-t-p-l-n-HQTCSDL/assets/168658766/648e7212-d015-44ae-85f6-9c5cf0dd459d)

  3.Quản lý hàng hóa 

  ![image](https://github.com/PhatKuriKaraDivincarnate/B-i-t-p-l-n-HQTCSDL/assets/168658766/3f282052-e244-4b3c-958f-05c9343aff4b)

  4.Quán lý bán hàng 

  ![image](https://github.com/PhatKuriKaraDivincarnate/B-i-t-p-l-n-HQTCSDL/assets/168658766/66983f64-8d31-44b2-948a-73a7d80f5a70)

  ** SỬ DỤNG CÁC CHỨC NĂNG 

  1.Thêm đơn hàng mới 

 ![image](https://github.com/PhatKuriKaraDivincarnate/B-i-t-p-l-n-HQTCSDL/assets/168658766/b4f6a3b8-eb92-447a-86eb-082ded2c0eb0)

  Kết Quả : 

  ![image](https://github.com/PhatKuriKaraDivincarnate/B-i-t-p-l-n-HQTCSDL/assets/168658766/8ae9883d-ef47-47bd-8619-756b15a2b33b)

  2.Thêm chi tiết đơn hàng mới 

  ![image](https://github.com/PhatKuriKaraDivincarnate/B-i-t-p-l-n-HQTCSDL/assets/168658766/44ae698a-96ab-4a5e-becb-0482df5126f6)

  Kết Quả : 

  ![image](https://github.com/PhatKuriKaraDivincarnate/B-i-t-p-l-n-HQTCSDL/assets/168658766/d6641c10-b610-439d-800f-e218fbca8bd0)

  3.Xóa chi tiết đơn hàng 

  ![image](https://github.com/PhatKuriKaraDivincarnate/B-i-t-p-l-n-HQTCSDL/assets/168658766/b8c6acdf-45c3-49df-899a-69c00c4387ba)

  Kết quả : 

  ![image](https://github.com/PhatKuriKaraDivincarnate/B-i-t-p-l-n-HQTCSDL/assets/168658766/ae98245f-9a87-46c2-8d54-051cab4f8724)
  
  đã xóa thành công 

** Một số Trigger sử dụng trong bài toán quản lý 

1.Kiểm tra số lượng hàng còn trong kho hàng ( nếu số lượng ít hơn đơn hàng thì không thêm được đơn hàng )

  ![image](https://github.com/PhatKuriKaraDivincarnate/B-i-t-p-l-n-HQTCSDL/assets/168658766/26b63e7b-9b3d-40f0-915a-aa7637213e1a)

2.Cập nhật số lượng hàng trong khó khi có đơn đặt hàng mới

![image](https://github.com/PhatKuriKaraDivincarnate/B-i-t-p-l-n-HQTCSDL/assets/168658766/ce0024b1-6965-4a04-b61e-0a9e318484f5)

3.Cập nhật giá trị đơn hàng khi có thay đổi trong chi tiết đơn hàng 

![image](https://github.com/PhatKuriKaraDivincarnate/B-i-t-p-l-n-HQTCSDL/assets/168658766/2cb93ae1-ceeb-40e0-9256-1e8f5d2890ac)










  





  

  


  



  



