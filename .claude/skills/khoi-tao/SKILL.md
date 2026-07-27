---
name: khoi-tao
description: Dùng vào Ngày 1 khi cài đặt AIS-OS, khi ai đó nói "khởi tạo giúp tôi", "khởi động giúp tôi", "setup giúp tôi", "onboard tôi", "bắt đầu thôi", "điền vào AIOS của tôi", hoặc vừa mới clone bộ kit này. Một trình thiết lập kết hợp — chạy buổi phỏng vấn 7 câu hỏi VÀ dựng bộ file Ngày-1 ở cuối quá trình. Có thể chạy lại nhiều lần (idempotent) — chạy lại bất cứ lúc nào sau khi sửa phong-van.md.
---

## Kỹ năng này làm gì

Một trình thiết lập kết hợp duy nhất. Đọc hoặc viết vào `phong-van.md` (file tiếp nhận thông tin gốc), thực hiện buổi phỏng vấn 7 câu hỏi nếu file chưa được điền, sau đó dựng bộ file Ngày-1 ngay trong cùng lần chạy. Không có một kỹ năng `/scaffold-from-intake` riêng — đây là một luồng duy nhất.

**Khoảnh khắc "wow":** ở cuối buổi, gợi ý câu hỏi kết thúc *"Hãy thử hỏi tôi: tôi nên tập trung vào gì trong tuần này?"* Người dùng chạy nó một lần. Đó chính là khoảnh khắc "wow". Không có kỹ năng `/today` riêng để lưu lại — câu hỏi đó tự nó đã gieo vào đầu người dùng khung tư duy Mindset (Default Shift) để họ tự thấm dần.

## Khi nào KHÔNG nên chạy kỹ năng này

- Nếu người dùng đã chạy `/khoi-tao` rồi và muốn làm mới: vẫn chạy, nhưng bỏ qua các câu hỏi đã có câu trả lời (có thể chạy lại nhiều lần).
- Nếu người dùng muốn thêm một kết nối mới: đó không phải là việc khởi tạo (`/khoi-tao`) — hãy chỉ họ đến `ket-noi.md` để sửa trực tiếp, hoặc lên kế hoạch chạy Giai đoạn 2 của `/nang-cap`.

## Thực hiện

### Bước 1: Đọc file tiếp nhận thông tin (intake)

Đọc `phong-van.md`. Kiểm tra phần nào trong Q1-Q7 đã có nội dung so với phần còn để placeholder `[Câu trả lời của bạn ở đây]`.

- **Đã điền hết** → bỏ qua Bước 2, nhảy thẳng đến Bước 3 (dựng file).
- **Một phần đã điền** → hỏi người dùng: "Tôi thấy Q1, Q3, Q4 đã có câu trả lời. Bạn muốn điền tiếp phần còn lại ngay bây giờ, hay dựng file từ những gì đã có?" Để họ tự quyết định.
- **Chưa điền gì (vừa clone xong)** → thực hiện Bước 2 theo cách trò chuyện tự nhiên.

### Bước 2: Buổi phỏng vấn (7 câu hỏi, giới hạn cứng)

Hỏi từng câu một. Ghi câu trả lời vào `phong-van.md` ngay khi có (để người dùng có thể tiếp tục nếu bị gián đoạn).

**Câu 1 — Bạn là ai, bạn bán gì, bạn bán cho ai?**
Danh tính, sản phẩm/dịch vụ, khách hàng mục tiêu (ICP). Mỗi phần một đoạn ngắn là đủ.

**Câu 2 — Dán 1-2 đoạn bạn đã viết gần đây. Không sửa lại.**
*Đây là câu hỏi duy nhất có một quy tắc cứng.* Các mẫu văn phong PHẢI được dán nguyên văn, không được gõ lại giữa cuộc trò chuyện. Nếu người dùng bắt đầu gõ văn bản mới, hãy từ chối:

> *"Dừng lại — hãy dán nguyên văn. Nếu bạn gõ lại ở đây trong khi chúng ta đang nói chuyện, mẫu này đã bị 'nhuốm màu' bởi cuộc trò chuyện của chúng ta rồi. Mở email hoặc bài đăng LinkedIn gần nhất của bạn ở một tab khác và dán văn bản gốc, chưa sửa. Đây là quy tắc duy nhất tôi không thể nhượng bộ."*

Hỏi xin hai mẫu. Một email, một bài đăng. Hoặc hai mẫu của một trong hai loại.

**Câu 3 — 2-3 ưu tiên lớn nhất của bạn trong 90 ngày tới là gì?**
Ưu tiên theo quý. Phản biện lại nếu họ nói "phát triển doanh nghiệp của tôi" — yêu cầu họ nêu ra một con số, một hạn chót, hoặc một sản phẩm cụ thể.

**Câu 4 — Doanh thu thực sự đổ về đâu, và được theo dõi ở đâu?**
Có thể trả lời nhiều nơi. Map vào Nhóm Dữ liệu Bậc 1 số 1 (Doanh thu/Tài chính).

**Câu 5 — Bạn nói chuyện với khách hàng, đội ngũ, và thế giới bên ngoài ở đâu mỗi ngày?**
Email (Gmail/Outlook), Slack/Teams/Discord, tin nhắn riêng. Map vào Nhóm 2 + 4.

**Câu 6 — Các bản ghi âm cuộc họp, ghi chú, và tài liệu quan trọng nằm ở đâu?**
Map vào Nhóm 6 + 7.

**Câu 7 — Việc gì chiếm hết thời gian trong tuần của bạn, và bạn đang theo dõi công việc ở đâu?**
Nắm bắt nỗi đau lớn nhất (top_pain, dùng cho `/nang-cap` Ngày-14) + Nhóm 5 (công việc/dự án).

Nhóm 3 (Lịch/Calendar) được tự động suy luận từ Câu 5: Gmail → Google Cal; Outlook → Outlook Cal. Xác nhận lại ở Bước 3.

### Bước 3: Dựng bộ file Ngày-1

Khi phần tiếp nhận thông tin đã hoàn tất, tạo các file sau (hoặc cập nhật nếu chạy lại). Sao lưu bản gốc vào `archives/intake-{YYYY-MM-DD-HHMM}/` nếu đã có file từ trước.

1. **`context/about-me.md`** — từ Câu 1 (danh tính, vai trò) + Câu 7 (nỗi đau lớn nhất). Mỗi phần một đoạn ngắn.
2. **`context/about-business.md`** — từ Câu 1 (sản phẩm/dịch vụ, khách hàng mục tiêu) + Câu 4 (mô hình doanh thu). Một đoạn.
3. **`context/priorities.md`** — từ Câu 3. Danh sách đánh số, mỗi ưu tiên một dòng.
4. **`references/voice.md`** — từ Câu 2. Dán nguyên văn các mẫu kèm một tiêu đề ngắn giải thích cách dùng ("Hãy bám theo phong cách này khi soạn nội dung; không giả mạo văn phong của tôi trên nội dung công khai mà không cho tôi xem trước").
5. **`ket-noi.md`** — điền vào bảng 7 dòng từ các câu trả lời Q4-Q7. Mỗi dòng nhận `mechanism: chưa kết nối`, `auth: —`, `lần kiểm tra cuối: —`. Người dùng sẽ kết nối các hệ thống này vào Ngày 2.
6. **`CLAUDE.md`** — điền vào mọi placeholder `{{...}}`. Thay bằng tên người dùng, ưu tiên đã nêu, tóm tắt văn phong, và một tóm tắt ngắn về các kết nối.

### Bước 4: Màn hình kết thúc

In một màn hình duy nhất. Tối đa ba dòng:

```
✓ Ngày 1 hoàn thành. AIOS của bạn đã biết bạn là ai, bạn bán gì, điều gì quan trọng trong quý này, và bạn nói chuyện theo phong cách nào.

Hôm nay: hãy hỏi tôi — "tôi nên tập trung vào gì trong tuần này?"
Ngày mai: chọn một công cụ trong ket-noi.md và kết nối nó (cài MCP bằng tay hoặc viết một script API nhỏ + lưu references/{tool}-api.md).
Ngày 7: chạy /danh-gia để xem điểm số của bạn.
```

Khi người dùng chạy câu hỏi kết thúc ("tôi nên tập trung vào gì trong tuần này?"), hãy trả lời chỉ dựa vào các file bối cảnh mới. Đảm bảo:
- Danh sách 3 gạch đầu dòng về ưu tiên, theo phong cách văn phong từ Câu 2
- Mỗi gạch đầu dòng liên hệ lại với một ưu tiên 90-ngày đã nêu ở Câu 3
- Dòng cuối: *"Nếu tôi phải chọn một việc cho thứ Hai, đó sẽ là [X], vì [lý do từ các ưu tiên]. Bạn muốn tôi soạn nháp email đầu tiên không? Và — Default Shift có thể áp dụng ở đâu trong việc này? AI có thể được tận dụng đến mức nào ở việc này?"*

Câu hỏi Default Shift này gieo trước khung tư duy Mindset, trước khi `/nang-cap` chính thức giới thiệu nó vào Ngày 14.

## Các quy tắc thực hiện quan trọng

1. **Giới hạn 7 câu hỏi là không thể thương lượng.** Không thêm Câu 8 trong lúc trò chuyện.
2. **Việc dán mẫu văn phong không thể bị bỏ qua.** Nếu người dùng gõ mẫu giữa cuộc trò chuyện, hãy từ chối và yêu cầu họ dán từ bài viết thật.
3. **Dựng file một lần.** Sau khi Bước 2 kết thúc, viết các file ở Bước 3 trong một lần duy nhất. Không cần xác nhận qua nhiều lượt. Người dùng lặp lại bằng cách sửa `phong-van.md` và chạy lại.
4. **Có thể chạy lại nhiều lần (idempotent).** Chạy lại với intake đã sửa sẽ làm mới các file bối cảnh; sao lưu bản gốc vào `archives/intake-{ts}/`. Bỏ qua các câu hỏi đã có câu trả lời trừ khi người dùng muốn sửa lại.
5. **Màn hình kết thúc chỉ ba dòng.** Không phải một menu.
6. **Không tạo thêm kỹ năng nào khác.** Không dựng thêm `/today`, `/draft`, `/connect`, v.v. Bộ kit chỉ có 3 kỹ năng; người dùng tự tạo thêm qua `/nang-cap`.
7. **Chỉ đọc với `references/3ms-framework.md`.** File này đã có sẵn trong bộ kit. Không ghi đè lên nó.
8. **Không viết vào `.env`.** Không hỏi khoá API vào Ngày 1. Việc kết nối sẽ đến vào Ngày 2.

## Kiểm chứng (cho người triển khai)

- Kiểm tra "lạnh": clone một bộ kit mới, chạy `/khoi-tao`, điền 7 câu trả lời, dựng file xong, hỏi câu kết thúc, câu trả lời trích dẫn cụ thể từ Câu 1 + Câu 3 + Câu 7. Trả lời chung chung = thất bại.
- Kiểm tra chạy lại nhiều lần: chạy lại `/khoi-tao` với một ưu tiên ở Câu 3 đã đổi. Kỳ vọng: chỉ `context/priorities.md` và phần ưu tiên trong `CLAUDE.md` được cập nhật; bản sao lưu được tạo ở `archives/intake-{ts}/`.
- Kiểm tra từ chối mẫu gõ giữa chừng: gõ một mẫu giữa cuộc trò chuyện. Kỳ vọng: kỹ năng từ chối, yêu cầu dán lại.

> *Chuyển thể từ The Three Ms of AI™ © 2026 Nate Herk. Ngôn ngữ Mindset dùng ở màn hình kết thúc lấy từ `references/3ms-framework.md`.*
