# Database Design

## 1 - Database Diagram

![database diagram](../images/img-db-diagram.png)

## 2 - Database specification

### 2.1 - List of Tables

| No     | Table name            | Description                               |
| :----: | :-------------------- | :---------------------------------------- |
| 1      | loaitaikhoan          | thông tin phần quyền của tài khoản        |
| 2      | taikhoan              | thông tin tài khoản                       |
| 3      | hangsanxuat           | thông tin hãng sản xuất                   |
| 4      | loaisanpham           | thông tin danh mục sản phẩm               |
| 5      | sanpham               | thông tin sản phẩm                        |
| 6      | tinhtrang             | thông tin tình trạng của đơn đặt hàng     |
| 7      | dondathang            | thông tin đơn đặt hàng                    |
| 8      | chitietdondathang     | thông tin chi tiết đơn đặt hàng           |


### 2.2 - Table structure

2.2.1 - Table: ***loaitainkhoan***

| No     | Field name            | Data type     | Key (PK/FK)  | Description                               |
| :----: | :-------------------- | :-----------: | :----------: | :---------------------------------------- |
| 1      | maloaitaikhoan        | int           | PK           | mã loại tài khoản                         |
| 2      | tenloaitaikhoan       | varchar(45)   |              | tên loại tài khoản                        |

2.2.2 - Table: ***taikhoan***

| No     | Field name            | Data type     | Key (PK/FK)  | Description                               |
| :----: | :-------------------- | :-----------: | :----------: | :---------------------------------------- |
| 1      | mataikhoan            | int           | PK           | mã tài khoản                              |
| 2      | tendangnhap           | varchar(20)   |              | tên đăng nhập                             |
| 3      | matkhau               | char(41)      |              | mật khẩu, sử dụng hàn PASSWORK để Hash    |
| 4      | tenhienthi            | varchar(64)   |              | tên hiển thị của tài khoản                |
| 5      | diachi                | varchar(256)  |              | địa chỉ của user                          |
| 6      | diẹnthoai             | varchar(11)   |              | số điện thoại của user                    |
| 7      | email                 | varchar(30)   |              | địa chỉ email của user                    |
| 8      | bixoa                 | bool          |              | cở đánh dấu xoá (soft-delete)             |
| 9      | maloaitaikhoan        | int           | FK           | mã loại tài khoản                         |

2.2.3 - Table: ***hangsanxuat***

| No     | Field name            | Data type     | Key (PK/FK)  | Description                               |
| :----: | :-------------------- | :-----------: | :----------: | :---------------------------------------- |
| 1      | mahangsanxuat         | int           | PK           | mã hãng sản xuất                          |
| 2      | tenhangsanxuat        | varchar(64)   |              | tên hãng sản xuất                         |
| 3      | logourl               | varchar(45)   |              | đường dẫn url của logo hãng sản xuất      |
| 4      | bixoa                 | bool          |              | cở đánh dấu xoá (soft-delete)             |

2.2.4 - Table: ***loaisanpham***

| No     | Field name            | Data type     | Key (PK/FK)  | Description                               |
| :----: | :-------------------- | :-----------: | :----------: | :---------------------------------------- |
| 1      | maloaisanpham         | int           | PK           | mã loại sản phẩm                          |
| 2      | tenloaisanpham        | varchar(64)   |              | tên loại sản phẩm                         |
| 3      | bixoa                 | bool          |              | cở đánh dấu xoá (soft-delete)             |

2.2.5 - Table: ***sanpham***

| No     | Field name            | Data type     | Key (PK/FK)  | Description                               |
| :----: | :-------------------- | :-----------: | :----------: | :---------------------------------------- |
| 1      | masanpham             | int           | PK           | mã sản phẩm                               |
| 2      | tensanpham            | varchar(45)   |              | tên sản phẩm                              |
| 3      | hinhurl               | varchar(45)   |              | đường dẫn url đến file ảnh của sản phẩm   |
| 4      | giasanpham            | int           |              | giá sản phẩm                              |
| 5      | ngaynhap              | datetime      |              | ngày nhập sản phẩm                        |
| 6      | soluongton            | int           |              | số lượng sản phẩm tồn kho hiện tại        |
| 7      | soluongban            | int           |              | số lượng sản phẩm đã bán                  |
| 8      | soluotxem             | int           |              | số lượt xem thông tin chi tiết            |
| 9      | mota                  | text          |              | các thông tin mô tả bổ sung của sẩn phẩm  |
| 10     | bixoa                 | bool          |              | cở đánh dấu xoá (soft-delete)             |
| 11     | maloaisanpham         | int           | FK           | mã loại sản phẩm                          |
| 12     | mahangsanxuat         | int           | FK           | mã hãng sản xuất                          |

2.2.6 - Table: ***tinhtrang***

| No     | Field name            | Data type     | Key (PK/FK)  | Description                               |
| :----: | :-------------------- | :-----------: | :----------: | :---------------------------------------- |
| 1      | matinhtrang           | int           | PK           | mã tình trạng                             |
| 2      | tentinhtrang          | varchar(45)   |              | tên tình trạng                            |

2.2.7 - Table: ***dondathang***

| No     | Field name            | Data type     | Key (PK/FK)  | Description                               |
| :----: | :-------------------- | :-----------: | :----------: | :---------------------------------------- |
| 1      | madondathang          | int           | PK           | mã đơn đặt hàng                           |
| 2      | ngaylap               | datetime      |              | ngày lập đơn đặt hàng                     |
| 3      | tongthanhtien         | int           |              | tổng thành tiền của đơn đặt hàng          |
| 4      | mataikhoan            | int           | FK           | mã tài khoản của khách hàng đẵ đặt đơn    |
| 5      | matinhtrang           | int           | FK           | mã tình trạng hiện tại của đơn đặt hàng   |

2.2.8 - Table: ***chitietdondathang***

| No     | Field name            | Data type     | Key (PK/FK)  | Description                               |
| :----: | :-------------------- | :-----------: | :----------: | :---------------------------------------- |
| 1      | machitietdondathang   | int           | PK           | mã chi tiết đơn đặt hàng                  |
| 2      | soluong               | int           |              | số lượng sản phẩm được bán trong đơn hàng |
| 3      | giaban                | int           |              | giá bán                                   |
| 4      | madondathang          | int           | FK           | mã đơn đặt hàng                           |
| 5      | masanpham             | int           | FK           | mã sản phẩm                               |