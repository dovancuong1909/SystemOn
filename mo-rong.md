# Mở rộng — những gì nên thêm khi bạn phát triển hơn

Bộ kit này được thiết kế tinh gọn một cách có chủ đích. Ba kỹ năng, sáu thư mục, một tài liệu tham khảo khung tư duy. Vậy là đủ. Khi bạn sử dụng nó, bạn sẽ vượt ra ngoài nền tảng cơ bản — tài liệu này cho bạn biết nên thêm gì, khi nào, và vì sao.

Cấu trúc AIOS nên trông giống như một doanh nghiệp nhỏ được vận hành gọn gàng. Không phải như một cái hầm chứa đồ của người thích tích trữ.

---

## Những gì có sẵn trong bộ kit (đừng xoá)

| Thư mục / file | Mục đích |
|---|---|
| `context/` | Thông tin về bạn, doanh nghiệp của bạn, các ưu tiên của bạn. Được `/khoi-dong` điền vào. |
| `references/` | Các khung tư duy, mẫu văn phong, hướng dẫn API, quy trình chuẩn (SOP) khi bạn xây dựng chúng. |
| `quyet-dinh/nhat-ky.md` | Nhật ký chỉ-thêm-không-xoá ghi lại quyết định gì và vì sao. |
| `archives/` | File cũ. Không xoá — chuyển vào đây. |
| `ket-noi.md` | Danh sách mọi hệ thống mà AIOS của bạn có thể truy cập. |
| `.claude/skills/` | Các kỹ năng của bạn: `/khoi-dong`, `/danh-gia`, `/nang-cap`. Thêm kỹ năng mới qua `/nang-cap`. |
| `phong-van.md` | Nguồn dữ liệu gốc cho `/khoi-dong`. Sửa và chạy lại bất cứ lúc nào. |
| `CLAUDE.md` | Cẩm nang vận hành gốc. Được `/khoi-dong` điền vào. Sửa khi vai trò/văn phong của bạn thay đổi. |

---

## Những gì nên thêm khi bạn phát triển hơn

| Thư mục / file | Thêm khi nào | Vì sao |
|---|---|---|
| `projects/` | Bạn bắt đầu chạy 2+ luồng công việc (workstream) đang diễn ra, mỗi luồng có bối cảnh riêng | Các dự án đang hoạt động cần bối cảnh riêng biệt, khác với các file thông tin lâu dài trong `context/` |
| `templates/` | Bạn nhận thấy mình hay copy-paste lại các prompt hoặc khung tài liệu giống nhau | Các điểm khởi đầu có thể tái sử dụng, có thể tham số hoá; giúp giảm sự lệch lạc theo thời gian |
| `brand-assets/` | Bạn tạo ra nội dung hình ảnh (carousel, slide, thumbnail, hình ảnh) | Tập trung logo, bảng màu, font chữ, văn phong/tông giọng — AIOS sẽ tự tra cứu thay vì đoán |
| `references/sops/` | Bạn ghi lại cách các quy trình lặp lại được thực hiện | Quy trình vận hành chuẩn (SOP) mà AIOS đọc để thực hiện công việc một cách nhất quán |
| `references/{tool}-api.md` | Bạn kết nối một API hoặc MCP mới và tìm hiểu cách nó hoạt động | Nghiên cứu một lần, lưu lại mãi mãi. `/danh-gia` sẽ ghi nhận điều này; các kỹ năng sau không cần nghiên cứu lại. |
| `scripts/` | Bạn viết Python hoặc Bash để gọi các API chưa có MCP hỗ trợ | Với hầu hết mọi người, kết nối thứ hai là một script, không phải một MCP |
| `.claude/agents/` | Bạn cần một trợ lý phụ (sub-assistant) cho việc nghiên cứu/viết lách nhiều bước, lặp lại được | Các agent chạy trên các model rẻ hơn trong bối cảnh riêng của chúng — giúp phiên làm việc chính của bạn gọn nhẹ |
| Các thư mục hệ-điều-hành-con (ví dụ: `youtube-os/`) | Bạn có một mảng công việc chuyên biệt (vertical) với dữ liệu, sheet, bản ghi, script riêng | Mô hình tách biệt — các luồng công việc chuyên biệt có cẩm nang vận hành + kỹ năng riêng, có phạm vi giới hạn |

---

## Nhịp độ gợi ý

Khi nào mỗi khu vực nên được cập nhật thường xuyên:

- `quyet-dinh/nhat-ky.md` — mỗi quyết định có ý nghĩa (Phase 2 của `/nang-cap` tự động ghi lại các quyết định này)
- `archives/` — dọn dẹp theo quý; chuyển các dự án cũ, kỹ năng đã ngừng dùng, các phiên bản intake cũ vào đây
- `references/sops/` — khi một quy trình được người mới chạy lại, hãy viết SOP cho nó
- `ket-noi.md` — mỗi khi một công cụ mới được kết nối, thêm một dòng vào đây
- `references/{tool}-api.md` — cùng lúc với việc cập nhật `ket-noi.md`; ghi lại API đó một lần
- `CLAUDE.md` — xem lại theo quý; viết lại phần vai trò/ưu tiên sau khi `/nang-cap` chạy đến câu hỏi Q90

---

## Những gì KHÔNG nên thêm

Các kiểu chống-mẫu (anti-pattern). Trông như hữu ích nhưng sẽ làm mục nát cấu trúc:

- **Không đổ nguyên các bản lưu email/Slack thô vào `references/`.** Đây không phải là nơi đổ rác tài liệu. Chỉ lưu các sự kiện đã được diễn giải.
- **Không xây thư-mục-lồng-thư-mục để "diễn" tổ chức.** Cấu trúc phẳng với cách đặt tên tốt thắng việc lồng nhau sâu. Nếu bạn cần một cây thư mục phức tạp để tìm thấy thứ gì đó, đó là vấn đề tìm kiếm, không phải vấn đề tổ chức.
- **Không thêm `notes/`, `misc/`, `tmp/`, hay `inbox/`.** Đây là những "nghĩa địa". Dùng `archives/` nếu nó cũ, viết một file thật vào đúng chỗ nếu nó mới.
- **Không tạo trước các thư mục mà bạn chưa cần.** Thư mục trống chỉ là nhiễu. AIOS sẽ báo cho bạn biết khi nào nên tạo.
- **Không để song song hai file `quyet-dinh/nhat-ky.md` và `quyet-dinh/nhat-ky.md`.** Chọn một. Bộ kit này dùng `quyet-dinh/nhat-ky.md`.
- **Không tách (fork) cẩm nang vận hành của bạn ra nhiều bản.** Chỉ một `CLAUDE.md` ở thư mục gốc. Các thư mục hệ-điều-hành-con có thể có `CLAUDE.md` riêng với phạm vi hẹp, nhưng bản ở gốc luôn là bản chính thức.

---

## Cách nhận biết khi nào nên thêm một thư mục mới

Hãy tự hỏi ba câu:

1. **Đây có phải là một khái niệm hoàn toàn mới?** Hay nó có thể nằm trong một chỗ đã có sẵn?
2. **Tôi sẽ dùng đến nó 3 lần trở lên trong tháng tới không?** Nếu không, còn quá sớm để thêm.
3. **`/nang-cap` có thể tự nhiên dẫn một kỹ năng tương lai vào đây không?** Nếu có, AIOS sẽ sử dụng nó. Nếu không, bạn đang tổ chức cho chính mình, không phải cho hệ thống.

Hai câu trả lời "có" = nên thêm. Một câu trả lời "có" = hãy chờ.

---

> *Cấu trúc AIOS của bạn nên trông như một doanh nghiệp nhỏ được vận hành gọn gàng — không phải như hầm chứa đồ của người thích tích trữ. Khi bạn không tìm thấy thứ gì đó, đó là dấu hiệu để gộp lại, không phải để thêm một thư mục khác.*
