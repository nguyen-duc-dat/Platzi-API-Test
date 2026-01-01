#  RESTful API Testing & Automation with Postman - Platzi Store


## 📌 1. Giới thiệu (Introduction)
Dự án này tập trung vào **Kiểm thử API (API Testing)** và xây dựng các **Kịch bản tự động (Automated Test Scripts)** cho hệ thống Backend của trang thương mại điện tử **Platzi Fake Store API**.
Mục tiêu là đảm bảo chất lượng phần mềm thông qua việc kiểm thử chức năng (Functional Testing) và phát hiện các lỗ hổng bảo mật (Security Testing/Broken Access Control) bằng các script tự động hóa.

- **Hệ thống kiểm thử (SUT):** [Platzi Fake Store API](https://fakeapi.platzi.com/)
- **Công cụ thực hiện:** Postman, JavaScript (Tests scripts).
- **Phương pháp:** Black-box Testing, REST API Testing.

## 🛠 2. Công cụ & Kỹ thuật (Tech Stack)
Trong dự án này, sử dụng Postman làm công cụ chủ đạo để thiết kế và tự động hóa quy trình test:
- **Postman:** Thiết kế Request, quản lý cấu trúc Collections và Environments.
- **Collection Runner:** Thực thi hàng loạt kịch bản kiểm thử (Batch execution) để kiểm tra hồi quy.
- **JavaScript (Chai Assertion):** Viết các đoạn mã kiểm tra (Test Scripts) trong Postman để verify:
    - Status Code (200, 201, 400, 401...).
    - Response Time (< 2000ms).
    - JSON Schema Validation.
    - Business Logic (Giá trị trả về khớp với dữ liệu tạo ra).
- **Dynamic Variables:** Sử dụng biến môi trường để truyền dữ liệu động giữa các Request (Chaining Requests).

## 3. Phạm vi kiểm thử (Test Scope)
Bộ kịch bản bao gồm **39 Test Cases**, bao phủ các module chính:

### ✅ Module Authentication (Xác thực)
- Đăng nhập (Login) thành công/thất bại.
- Kiểm tra cơ chế sinh Token (JWT) và Refresh Token.
- Kiểm tra truy cập tài nguyên bảo mật (User Profile).

### ✅ Module Products (Sản phẩm)
- **CRUD Flow:** Tạo mới -> Xem chi tiết -> Cập nhật -> Xóa.
- **Data Validation:** Kiểm tra giá trị âm, sai kiểu dữ liệu.
- **Security Test:** Kiểm tra User thường có xóa được sản phẩm của Admin không.

### ✅ Module Categories (Danh mục)
- Kiểm tra danh sách danh mục.
- Kiểm tra phân quyền tạo/xóa danh mục.

## 4. Kết quả thực nghiệm (Test Results)
Sau khi thực thi bộ Script trên môi trường Production, kết quả thu được như sau:

| Metric | Số lượng | Tỷ lệ |
| :--- | :---: | :---: |
| **Tổng số Test Cases** | 39 | 100% |
| ✅ **Passed (Đạt)** | 33 | 84.6% |
| ❌ **Failed (Lỗi)** | 6 | 15.4% |

> **Lưu ý:** 6 Test Cases bị Failed thực chất là các **Lỗ hổng bảo mật (Security Bugs)** Negative Testing. Hệ thống cho phép User thường thực hiện các quyền của Admin (Lỗi 200 OK thay vì 401/403).

## 🐞 5. Báo cáo lỗi (Bug Report)
Phân tích và log chi tiết các lỗi bảo mật nghiêm trọng (Critical/High Severity) kèm theo bằng chứng (Evidence) tại file báo cáo dưới đây:

👉 **[BẤM VÀO ĐÂY ĐỂ XEM BUG REPORT CHI TIẾT (GOOGLE SHEETS)](https://docs.google.com/spreadsheets/d/1hPooKZNsVRuTnhPMOSfZIv8myvqrdQEMCnh98MaPwls/edit?usp=sharing)**

## 6. Cấu trúc Repository (Files)
- **`API_testing_platzi.docx`**: Báo cáo tổng hợp dự án (Full Report) - Phân tích chi tiết chiến lược và kết quả.
- **`Platz_Collection.json`**: Source Code (Collection) chứa toàn bộ kịch bản test.
- **`Platzi_env.json`**: File cấu hình biến môi trường (Base URL, Tokens...).

## 7. Hướng dẫn cài đặt & Chạy (How to run)
Để chạy thử dự án này trên máy của bạn:

1. **Cài đặt:** Tải và cài đặt [Postman](https://www.postman.com/downloads/).
2. **Clone/Download:** Tải 2 file `.json` trong repository này về máy.
3. **Import:**
   - Mở Postman -> Bấm **Import** -> Chọn 2 file vừa tải.
4. **Cấu hình:**
   - Chọn Environment là **"Platzi Env"** (góc trên bên phải).
5. **Thực thi:**
   - Bấm vào tên Collection **"Platzi_Ecommerce_Automation"**.
   - Chọn **Run Collection**.
   - Bấm **Run Platzi...** và xem kết quả.

---
**Author:** Nguyễn Đức Đạt
**Contact:** nguyenduc01012k@gmail.com
**LinkedIn:** [Nguyễn Đức Đạt](https://www.linkedin.com/in/%C4%91%E1%BB%A9c-%C4%91%E1%BA%A1t-nguy%E1%BB%85n-01577431a/)
