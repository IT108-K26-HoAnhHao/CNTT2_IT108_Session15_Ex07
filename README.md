## Phần 1: Phân tích vấn đề

### 1. Bảng phân tích rủi ro và nguyên nhân cho các hạng mục tài liệu

| Hạng mục tài liệu | Rủi ro mất mát dữ liệu (%) | Nguyên nhân gốc rễ | Xếp loại |
| :--- | :--- | :--- | :--- |
| **Business Plan (20 trang)** | **Cao (100%)** | Lưu trữ cục bộ trên duy nhất một thiết bị không có bản sao dự phòng (Nguyên nhân công nghệ) kết hợp thiếu quy trình quản lý file tập trung của nhóm (Nguyên nhân tổ chức). | Cao |
| **Mã nguồn giao diện (HTML/CSS)** | **Cao** | Phụ thuộc vào thiết bị lưu trữ di động (USB flash drive) dễ bị hỏng, thất lạc và không được đồng bộ lên kho lưu trữ chung. | Cao |
| **Database danh sách test user** | **Cao** | Lưu file thủ công trên máy cá nhân, không có cơ chế tự động sao lưu định kỳ, dẫn đến việc dùng bản cũ từ 2 tuần trước. | Cao |
| **Slide Pitch (PowerPoint)** | **Trung bình** | Sử dụng đám mây (Zalo cloud) nhưng quản lý tên phiên bản thủ công hỗn loạn (`v7_final_FINAL.pptx`), gây nhầm lẫn về tính xác thực của bản mới nhất. | Trung bình |
| **Tài liệu SRS (Word)** | **Trung bình** | Trao đổi qua email đính kèm làm phân mảnh lịch sử chỉnh sửa, không kiểm soát được đâu là phiên bản chính thức cuối cùng. | Trung bình |

### 2. Hiện tượng "23 phiên bản file tồn tại trên nhiều thiết bị"
* **Tên gọi trong kỹ thuật:** **Phân mảnh phiên bản (Version Fragmentation)** hoặc **Xung đột phiên bản / Quản lý phiên bản thủ công kém**.
* **Nguyên nhân:** Do các thành viên gửi file qua lại qua ứng dụng nhắn tin (Zalo) và trưởng nhóm thao tác thủ công (tải về, sửa, lưu, gửi lại). Không có hệ thống quản lý mã nguồn hoặc không gian lưu trữ đồng bộ chung để tự động quản lý lịch sử chỉnh sửa (*Version Control*).
* **Hậu quả đối với dự án phần mềm thực tế:**
  * **Xung đột mã nguồn/tài liệu (Conflict):** Dễ ghi đè lên các thay đổi mới của nhau, làm mất mã nguồn hoặc nội dung đã cập nhật.
  * **Lãng phí thời gian:** Mất nhiều thời gian để kiểm tra, đối chiếu xem đâu là file mới nhất, chuẩn xác nhất.
  * **Rủi ro vận hành cao:** Dễ dẫn đến việc triển khai các tính năng cũ hoặc sai lệch khi thuyết trình hoặc bàn giao sản phẩm.

---

## Phần 2: Sửa lỗi & Nghiệm thu

### 3. Quy trình Hybrid Workflow cho nhóm CampusPay

#### Sơ đồ 3 bước vận hành Hybrid Workflow:
```text
[1. Làm việc Local (SSD)] --(Nhấn Ctrl+S / Lưu file)--> [2. Auto Sync (Google Drive / OneDrive)] --(Đồng bộ ngầm qua mạng)--> [3. Cloud Storage (Lưu trữ đám mây)]