---
name: nang-cap
description: Dùng hàng tuần để tìm và hoàn thành một tự động hoá mới. Đi qua buổi phỏng vấn 3Ms — Mindset (tìm ứng viên) → Method (xác định phạm vi cho một việc) → Machine (xây dựng nó). Kích hoạt khi nghe "nâng cấp", "let's level up", "tôi nên tự động hoá gì tiếp theo", "tìm cho tôi một lợi thế trong tuần này", hoặc dùng như nghi thức thứ Sáu hàng tuần. Một lần chạy = một sản phẩm hoàn thành.
---

> *Chuyển thể từ The Three Ms of AI™. © 2026 Nate Herk. Mọi quyền được bảo lưu.*
> *The Three Ms of AI™ là thương hiệu đã đăng ký của Nate Herk.*

## Kỹ năng này làm gì

Dẫn người dùng đi qua 3Ms mỗi tuần để tìm ra và hoàn thành một tự động hoá mới. **Một buổi phỏng vấn = một sản phẩm.** Kỹ năng này cũng dần "cài đặt" khung tư duy 3Ms vào đầu người dùng theo thời gian — sau 4-6 lần chạy, người dùng bắt đầu tự nhận ra cơ hội tự động hoá giữa tuần mà không cần được nhắc, vì các câu hỏi đã trở thành phản xạ tự nhiên của họ.

Đây là cơ chế "lập trình lại bộ não". Bộ kit không cần cron job để neo giữ hành vi này; nó cần `/nang-cap` được chạy đều mỗi thứ Sáu.

## `/nang-cap` KHÔNG phải là gì

- Không phải `/danh-gia`. `/danh-gia` mang tính cấu trúc ("AIOS đã được xây đúng cách chưa?"). `/nang-cap` mang tính chức năng ("tôi đang thiếu lợi thế kinh doanh gì?"). Hãy chạy `/danh-gia` trước nếu cấu trúc còn lộn xộn.
- Không phải một công cụ lập kế hoạch nhiều ứng viên cùng lúc. Một lần chạy = một sản phẩm hoàn thành.
- Không phải một huấn luyện viên (coach). Người dùng là người suy nghĩ. Kỹ năng này chỉ dẫn dắt buổi phỏng vấn.

## Khi nào `/nang-cap` nên chạy

- **Lần đầu: Ngày 14.** Sau khi người dùng đã kết nối ≥1 MCP/script và chạy `/danh-gia` một lần. Chạy sớm hơn sẽ cho ra kết quả hời hợt.
- **Nhịp độ: hàng tuần, chiều thứ Sáu.** Nhìn lại tuần, tìm ra một việc để tự động hoá, hoàn thành vào thứ Hai.
- **Bất cứ lúc nào theo yêu cầu.** Giữa tuần, nếu một việc thủ công khiến bạn thấy "ngứa ngáy".

## Các dữ liệu đầu vào kỹ năng này đọc

- `context/priorities.md` — những gì người dùng nói là quan trọng
- `context/about-me.md` — nỗi đau lớn nhất (top_pain), vai trò
- `ket-noi.md` — những gì có thể truy cập được, bằng cơ chế nào
- `references/3ms-framework.md` — khung tư duy (dùng để trích dẫn lại các nguyên tắc)
- `quyet-dinh/nhat-ky.md` — các quyết định gần đây (những gì đã hoàn thành hoặc đã được xem xét)
- frontmatter của `.claude/skills/*/SKILL.md` — những năng lực hiện có
- `danh-gia/danh-gia-{date}.md` gần nhất, nếu có

## Thực hiện — ba giai đoạn (phase)

### Giai đoạn 1 — Phỏng vấn Mindset (tìm ứng viên)

Đưa ra 1-3 ứng viên, xếp theo mức ảnh hưởng. Hỏi theo thứ tự này, theo cách trò chuyện tự nhiên:

1. *"Kể tôi nghe về tuần của bạn. Bạn đã làm gì từ 3 lần trở lên?"* (tần suất)
2. *"Có việc gì cảm thấy thủ công, nhàm chán, hoặc lặp đi lặp lại copy-paste không?"* (sự nhàm chán)
3. *"Có việc gì mà bạn nghĩ 'một thực tập sinh thông minh có thể làm được' không?"* (khả năng giao việc)
4. *"Nếu ngày mai có 500 khách hàng mới xuất hiện, điều gì sẽ vỡ trận đầu tiên?"* (điểm nghẽn)
5. *"Điều gì sẽ mang lại cho bạn 500 khách hàng nữa vào ngày mai?"* (cơ hội tăng trưởng)

Trích dẫn các nguyên tắc Mindset liên quan khi phù hợp:
- *"Nghe như Default Shift đang áp dụng ở đây — AI có thể được tận dụng đến mức nào trong việc này?"*
- *"Đây là Function Breakdown — bạn không tự động hoá toàn bộ công việc, chỉ một mảnh này thôi."*
- *"AI tốt hơn bạn nghĩ và đang cải thiện nhanh hơn bạn nghĩ. Nếu nó không làm được việc này quý trước, có thể giờ nó đã làm được."*

**Đầu ra của Giai đoạn 1:** danh sách đánh số 1-3 cơ hội ứng viên, mỗi cơ hội kèm một dòng giải thích "vì sao đây là lợi thế". Hỏi: *"Chọn một để xác định phạm vi."*

### Giai đoạn 2 — Phỏng vấn Method (xác định phạm vi cho một việc)

Người dùng chọn một ứng viên. Đi qua pipeline Method gồm 5 bước:

**Bước 1 — Tìm nút thắt cổ chai.** Việc này giải quyết điểm nghẽn nào, hoặc mở ra cơ hội tăng trưởng nào? Liên hệ lại với câu trả lời ở Giai đoạn 1.

**Bước 2 — EAD: Loại bỏ / Tự động hoá / Giao việc.**
- **Loại bỏ trước:** *"Điều gì sẽ xảy ra nếu chúng ta chỉ đơn giản là ngừng làm việc này?"* Nếu câu trả lời là "không có gì hỏng cả" → kỹ năng kết thúc một cách vui vẻ. *"Đừng tự động hoá sự lãng phí."* Đây là một thắng lợi, hãy ghi vào `quyet-dinh/nhat-ky.md` và dừng lại.
- **Tự động hoá thứ hai:** áp dụng khung 60/30/10. ~60% xác định (deterministic), ~30% AI hỗ trợ, ~10% thủ công.
- **Giao việc thứ ba:** nếu quá phức tạp/biến động/cần nhiều xét đoán → gợi ý giao cho một người. Kỹ năng kết thúc với gợi ý giao việc, ghi lại quyết định này.

**Bước 3 — Sơ đồ hoá quy trình.** Năm yếu tố:
- Trigger (yếu tố kích hoạt — điều gì khởi động việc này)
- Data sources (nguồn dữ liệu — thông tin đến từ đâu)
- Data transformations (biến đổi dữ liệu — dữ liệu thay đổi hình dạng ra sao)
- Decision points (điểm quyết định — nơi nó phân nhánh)
- Destination (đích đến — kết quả đi về đâu)

Nếu người dùng không thể diễn đạt được bất kỳ yếu tố nào trong 5 yếu tố trên: *"Nếu bạn không thể giải thích nó cho một người, bạn không thể giải thích nó cho AI. Hãy sơ đồ hoá nó trên giấy trước, rồi quay lại."* Kỹ năng dừng lại.

**Bước 4 — Chọn mức độ tự chủ.**

| Mức | Tên | Điều gì xảy ra |
|---|---|---|
| L0 | Manual (Thủ công) | Không có AI |
| L1 | Suggested (Gợi ý) | AI gợi ý, con người quyết định mỗi bước |
| L2 | Drafted (Soạn thử) | AI soạn nháp, con người xem lại và sửa |
| L3 | Supervised (Giám sát) | AI chạy, con người kiểm chứng định kỳ |
| L4 | Autonomous (Tự chủ hoàn toàn) | AI xử lý từ đầu đến cuối |

**Mặc định = mức thấp nhất mà vẫn giải quyết được vấn đề.** Phản biện lại nếu người dùng muốn chọn L4 ngay, trừ khi họ đã chạy qua các mức thấp hơn trước đó. *"Quy trình (workflow) thắng tác tử (agent). Nếu một quyết định không BẮT BUỘC phải do AI đưa ra, đừng để AI đưa ra quyết định đó."*

**Bước 5 — Gắn với một KPI.** Việc này thuộc nhóm nào trong Ba Nhóm chỉ số?
- Có thêm khách hàng
- Tăng giá trị mỗi khách hàng
- Giảm chi phí

Cùng với một chỉ số cụ thể (thời gian phản hồi, tỷ lệ lỗi, tỷ lệ chuyển đổi, thời gian hoàn thành). **Nếu người dùng không thể nêu tên một nhóm và một chỉ số, kỹ năng dừng lại.** *"Nếu tự động hoá của bạn không làm thay đổi một con số nào, vậy thì bạn xây nó để làm gì?"*

**Đầu ra của Giai đoạn 2:** đặc tả tự động hoá đã xác định phạm vi, được ghi vào `quyet-dinh/nhat-ky.md` thành một mục có ngày tháng kèm cả 5 câu trả lời + mức độ tự chủ + KPI. Đây là bản ghi lâu dài về điều gì đã được quyết định và vì sao.

### Giai đoạn 3 — Chuyển giao cho Machine (xây dựng)

Hỏi: *"Bạn muốn hoàn thành việc này theo cách nào?"* Các lựa chọn được xếp theo nguyên tắc Nhàm-chán-là-đẹp (Boring-is-Beautiful):

1. **Chỉ-prompt** — một mẫu prompt được lưu lại, người dùng tự chạy bằng tay. Không cần hạ tầng kỹ thuật. Cần nhiều sự can thiệp thủ công nhất.
2. **Kỹ năng xác định (deterministic skill)** — một file SKILL.md chạy một script (không có bước AI). Tốt nhất cho các biến đổi có quy tắc rõ ràng.
3. **Kỹ năng có AI hỗ trợ** — file SKILL.md có một lệnh gọi AI bên trong. Soạn nháp, phân loại, tóm tắt.
4. **Sub-agent** — agent nhiều bước. Lựa chọn cuối cùng. Chỉ khi công việc thực sự cần lập luận + dùng công cụ.

**Lựa chọn mặc định = phương án không-dùng-AI cao nhất mà vẫn giải quyết được vấn đề.** Người dùng phải chủ động chọn mức tự chủ cao hơn.

Sau khi đã chọn, dẫn tới công cụ dựng khung (scaffolder) phù hợp:
- `skill-creator` nếu có sẵn ở phạm vi toàn cục (do Anthropic phát hành)
- `skill-builder` nếu người dùng có sẵn cục bộ
- Nếu không có, tự viết một file SKILL.md / agent trực tiếp kèm frontmatter, vị trí lưu, và nội dung

**Mọi sản phẩm được dựng khung đều có hai dòng tiêu đề này ở đầu:**

```markdown
---
bike-method-phase: 1  # Giai đoạn 1 — Bánh phụ. Chạy thủ công trước.
three-ms-attribution: |
  Chuyển thể từ The Three Ms of AI™ © 2026 Nate Herk.
---
```

Điều này khoá người dùng vào Giai đoạn 1 của Phương pháp xe đạp (Bike Method) ngay lần xây dựng đầu tiên. Họ không thể âm thầm bỏ qua bước kiểm chứng thủ công. Chỉ có thể nâng giai đoạn bằng cách sửa file một cách chủ động.

Nêu ra các nguyên tắc Machine khi dựng khung:
- **Nguyên tắc Lego** — các bước nhỏ nhất, không-AI trước nếu có thể
- **Chuỗi kiểm chứng** — kiểm tra mỗi bước trước khi nối lại
- **Tư duy lặp lại cải tiến** — hoàn thành bản POC, mở rộng từ việc sử dụng thực tế

## Hợp đồng đầu ra (Output contract)

Mỗi lần chạy `/nang-cap` tạo ra:

1. **Một mục trong `quyet-dinh/nhat-ky.md`** — có ngày tháng, kèm đặc tả Method
2. **Một sản phẩm đã được dựng khung** — prompt, kỹ năng, hoặc file agent
3. **Một màn hình tổng kết** — những gì đã được xác định phạm vi, những gì đã được xây dựng, và lời nhắc về Giai đoạn 1 của Bike Method

## Các quy tắc thực hiện quan trọng

1. **Một buổi phỏng vấn = một sản phẩm.** Không xác định phạm vi nhiều ứng viên song song.
2. **Giai đoạn Mindset luôn chạy trước.** Ngay cả khi người dùng đến với một ý tưởng đã định hình sẵn.
3. **EAD buộc phải "loại bỏ trước".** Nếu câu trả lời là Loại bỏ, kết thúc một cách vui vẻ — đó là một thắng lợi, không phải một thất bại.
4. **Mặc định chọn mức độ tự chủ thấp nhất mà vẫn hiệu quả.** Phản biện lại nếu người dùng muốn chọn L4 ngay.
5. **Mặc định Nhàm-chán-là-đẹp khi chuyển giao cho Machine.** Mặc định = phương án không-dùng-AI cao nhất.
6. **Gắn-với-KPI là bắt buộc.** Nếu người dùng không thể nêu tên nhóm + chỉ số, kỹ năng dừng lại.
7. **Bike Method được đưa vào mọi sản phẩm.** `bike-method-phase: 1` trong frontmatter.
8. **Chỉ đọc với các file của người dùng, trừ `quyet-dinh/nhat-ky.md` và sản phẩm mới.** Không sửa các file hiện có khác.
9. **Có ghi nhận thương hiệu + tác quyền trên đầu ra.** Mỗi báo cáo và mỗi sản phẩm được dựng khung đều tham chiếu đến khung tư duy này.

## Kiểm chứng (cho người triển khai)

- **Chạy thử trên Herk-2 của Nate** không kèm prompt. Kỳ vọng: kỹ năng nêu ra 2-3 ứng viên lấy từ hoạt động gần đây, ưu tiên, và nỗi đau lớn nhất (top_pain) của anh ấy. Đầu ra chung chung ("bạn nên xây một bản tóm tắt") = thất bại.
- **Kiểm tra "loại bỏ trước".** Đưa vào một ứng viên rõ ràng có thể loại bỏ được. Kỳ vọng: kỹ năng gợi ý Loại bỏ, kết thúc, ghi lại thắng lợi này.
- **Kiểm tra phản biện L4.** Người dùng yêu cầu một bộ trả-lời-email-tự-chủ-hoàn-toàn ngay lần xây đầu tiên. Kỳ vọng: kỹ năng nhấn mạnh cần chạy L1/L2 trước, không hoàn thành ở L4 nếu không có sự ghi đè (override) rõ ràng từ người dùng.
- **Kiểm tra Nhàm-chán-là-đẹp.** Ứng viên có thể giải quyết bằng Python xác định. Kỳ vọng: kỹ năng gợi ý `(2) kỹ năng xác định` làm mặc định.
- **Chống bỏ-qua-bước của Bike Method.** Người dùng dựng khung xong, yêu cầu nâng lên Giai đoạn 4 ngay lập tức. Kỳ vọng: kỹ năng buộc họ đọc ý nghĩa của mỗi giai đoạn và xác nhận đã kiểm chứng các giai đoạn thấp hơn.

---

> *The Three Ms of AI™ là thương hiệu đã đăng ký của Nate Herk. © 2026 Nate Herk. Mọi quyền được bảo lưu.*
