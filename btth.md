# [Vận dụng chuyên sâu] Thiết kế giải pháp Prompting ứng dụng thực tế cho Cấu trúc Prompt Tiêu chuẩn & Định dạng

**Yêu cầu đầu ra chi tiết**

**Bước 1: Thiết kế giải pháp (I/O)**

Xác định rõ Input của bài toán gồm những gì, và cấu trúc Output mong muốn.

Input (Đầu vào):
- Tên sản phẩm.
- Mã sản phẩm.
- Giá bán.
- Số lượng tồn kho.
- Thông tin khuyến mãi.
- Yêu cầu xử lý từ cửa hàng.
Output (Đầu ra):
- Thông tin sản phẩm được phân loại rõ ràng.
- Đánh giá tình trạng tồn kho.
- Đề xuất xử lý phù hợp.
- Xuất kết quả theo bảng Markdown hoặc JSON để dễ quản lý.

**Bước 2: Viết prompt và chạy thử**

Viết prompt hoàn chỉnh theo định dạng chuyên nghiệp và copy kết quả phản hồi của AI.    

Bạn là nhân viên quản lý dữ liệu của cửa hàng TechShop.

**Nhiệm vụ:** Tiếp nhận thông tin sản phẩm, kiểm tra giá bán, số lượng tồn kho và tình trạng khuyến mãi.

**Yêu cầu:**
- Phân loại sản phẩm theo tình trạng tồn kho.
- Đề xuất nhập thêm hàng nếu số lượng dưới 10.
- Sử dụng Few-shot theo ví dụ:
  - RAM 8GB, tồn kho 5 → Sắp hết hàng.
  - SSD 512GB, tồn kho 30 → Còn hàng.
- Xuất kết quả dưới dạng bảng Markdown gồm: Tên sản phẩm, Giá bán, Tồn kho, Tình trạng, Đề xuất.
- Không tự suy đoán thông tin còn thiếu.
- Trả lời ngắn gọn, chính xác.


## **Bước 2: Viết prompt và chạy thử**

**Prompt hoàn chỉnh:**

Bạn là nhân viên quản lý dữ liệu của cửa hàng TechShop.

**Nhiệm vụ:** Tiếp nhận thông tin sản phẩm, kiểm tra giá bán, số lượng tồn kho và tình trạng khuyến mãi.

**Yêu cầu:**

- Phân loại sản phẩm theo tình trạng tồn kho.
- Đề xuất nhập thêm hàng nếu số lượng dưới 10.
- Sử dụng Few-shot theo ví dụ:
  - RAM 8GB, tồn kho 5 → Sắp hết hàng.
  - SSD 512GB, tồn kho 30 → Còn hàng.
- Xuất kết quả dưới dạng bảng Markdown gồm: Tên sản phẩm, Giá bán, Tồn kho, Tình trạng, Đề xuất.
- Không tự suy đoán thông tin còn thiếu.
- Trả lời ngắn gọn, chính xác.

**Kết quả AI chạy thử:**

| Sản phẩm      | Giá bán    | Tồn kho | Tình trạng   | Đề xuất      |
| --- | --- | ------- | --- | --- |
| RAM 8GB       | 500.000đ   | 5       | Sắp hết hàng | Nhập thêm    |
| SSD 512GB     | 900.000đ   | 30      | Còn hàng     | Tiếp tục bán |
| Card RTX 4060 | 7.000.000đ | 0       | Hết hàng     | Nhập thêm    |

