# Kết nối (Connections)

Danh sách mọi hệ thống mà AIOS của bạn có thể truy cập. Được `/khoi-tao` điền vào từ các câu trả lời Q4-Q7; mở rộng dần theo thời gian khi bạn kết nối thêm công cụ mới. `/danh-gia` sẽ kiểm tra file này để đánh giá độ phủ và độ "tươi mới" của các kết nối.

| # | Nhóm (Domain) | Công cụ | Cơ chế kết nối | Xác thực (Auth) | Lần kiểm tra cuối |
|---|---|---|---|---|---|
| 1 | Doanh thu / Tài chính | _được /khoi-tao điền vào_ | chưa kết nối | — | — |
| 2 | Tương tác với khách hàng | _được /khoi-tao điền vào_ | chưa kết nối | — | — |
| 3 | Lịch (Calendar) | _được /khoi-tao điền vào_ | chưa kết nối | — | — |
| 4 | Giao tiếp | _được /khoi-tao điền vào_ | chưa kết nối | — | — |
| 5 | Theo dõi dự án / công việc | _được /khoi-tao điền vào_ | chưa kết nối | — | — |
| 6 | Thông tin từ cuộc họp | _được /khoi-tao điền vào_ | chưa kết nối | — | — |
| 7 | Kiến thức / tài liệu | _được /khoi-tao điền vào_ | chưa kết nối | — | — |

**Các lựa chọn cơ chế kết nối (Mechanism):** `mcp` (máy chủ MCP), `script` (Python/Bash gọi API, đặt trong `scripts/`), `export` (chuỗi xử lý xuất file CSV/JSON), `key+ref` (khoá API trong `.env` + hướng dẫn trong `references/{tool}-api.md`), `not yet connected` (chưa kết nối).

Khi bạn kết nối một công cụ mới, hãy lưu thêm `references/{tool}-api.md` ghi lại các endpoint, luồng xác thực, và các truy vấn thường dùng — nghiên cứu một lần, dùng được mãi mãi.
