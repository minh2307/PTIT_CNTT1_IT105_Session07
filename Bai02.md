1. kiến trúc 3 tầng tổng thể
Presentation Tier: (Web UI / Mobile App / Admin Dashboard)      
Business Logic Tier: (ProductService, SupplierService, InventoryMgr) 
Data Access Tier: (ProductDAO, SupplierDAO, Database)          

2. Mô tả logic từng tầng
    1. Presentation Tier (Tầng giao diện)
Chức năng:

Là nơi người dùng (nhân viên kho, quản lý) tương tác trực tiếp với hệ thống.

Gửi yêu cầu đến tầng logic nghiệp vụ và hiển thị kết quả trả về.

Thành phần chính:

ProductView: Giao diện hiển thị danh sách sản phẩm, thêm/sửa/xóa.

SupplierView: Giao diện quản lý nhà cung cấp.

InventoryView: Hiển thị thông tin nhập – xuất – tồn kho.

Công nghệ đề xuất:

Web: React / Angular / Vue.js

Mobile: Flutter / React Native

 2. Business Logic Tier (Tầng xử lý nghiệp vụ)

Chức năng:

Chứa toàn bộ logic xử lý của hệ thống như:

Xử lý nhập hàng, xuất hàng.

Cập nhật số lượng tồn kho.

Quản lý mối quan hệ giữa sản phẩm – nhà cung cấp.

Nhận yêu cầu từ Presentation Tier → xử lý → gửi kết quả đến Data Tier.

Các lớp chính:

ProductService: Xử lý thêm, sửa, xóa sản phẩm.

SupplierService: Xử lý thông tin nhà cung cấp.

InventoryService: Tính toán số lượng nhập – xuất – tồn kho.

OrderService: Xử lý đơn đặt hàng từ nhà cung cấp.

Công nghệ đề xuất:

Node.js / Java / Python (Spring Boot, ExpressJS, FastAPI,…)

3. Data Access Tier (Tầng dữ liệu)

Chức năng:

Chịu trách nhiệm lưu trữ, truy xuất dữ liệu từ cơ sở dữ liệu.

Che giấu chi tiết truy vấn SQL, chỉ cung cấp các hàm (API nội bộ) cho tầng logic gọi.

Các lớp chính:

ProductDAO (Data Access Object)

SupplierDAO

InventoryDAO

Database (MySQL / PostgreSQL)

Bảng dữ liệu chính:

Products(product_id, name, category, price, quantity)

Suppliers(supplier_id, name, contact_info)

StockEntries(entry_id, product_id, type, quantity, date)

type: nhập hoặc xuất

Tóm tắt
| Tầng           | Vai trò chính          | Thành phần ví dụ                 | Công nghệ gợi ý           |
| -------------- | ---------------------- | -------------------------------- | ------------------------- |
| Presentation   | Hiển thị, nhập dữ liệu | ProductView, SupplierView        | React, Flutter            |
| Business Logic | Xử lý nghiệp vụ        | ProductService, InventoryService | Java Spring Boot, Node.js |
| Data Access    | Giao tiếp DB           | ProductDAO, SupplierDAO          | MySQL, PostgreSQL         |

