# AIS-OS — Bảng câu hỏi tiếp nhận thông tin (Intake)

Đây là file nguồn dữ liệu gốc cho AIOS của bạn. Hãy điền vào bằng cách gõ chữ, dán bằng giọng nói (Wispr Flow / chức năng đọc-thành-chữ của hệ điều hành), hoặc chạy `/khoi-dong` để có một buổi trò chuyện hướng dẫn từng bước. Dù bằng cách nào, đây là file mà `/khoi-dong` sẽ đọc để dựng bộ thiết lập Ngày-1 của bạn.

**Giới hạn cứng: 7 câu hỏi.** Mỗi câu trả lời được trong vòng dưới 60 giây. Đừng suy nghĩ quá nhiều — bạn có thể sửa và chạy lại `/khoi-dong` bất cứ lúc nào.

---

## Câu 1 — Bạn là ai, bạn bán gì, bạn bán cho ai?

Danh tính, sản phẩm/dịch vụ, khách hàng mục tiêu (ICP). Mỗi phần một đoạn ngắn là đủ.

```
[Câu trả lời của bạn ở đây]
```

---

## Câu 2 — Dán 1-2 đoạn bạn đã viết gần đây. Không sửa lại.

Một email, một bài đăng LinkedIn, một tin nhắn (DM), một tài liệu — bất cứ thứ gì nghe giống "bạn" khi bạn không cố gắng thể hiện. **Dán nguyên văn.** Không gõ lại các đoạn này trong khi đang trò chuyện với Claude — các mẫu được "gõ theo kiểu trò chuyện" sẽ tệ hơn là không có mẫu nào cả (gây nhiễu văn phong).

```
[Mẫu 1 — dán nguyên văn]
```

```
[Mẫu 2 — dán nguyên văn]
```

---

## Câu 3 — 2-3 ưu tiên lớn nhất của bạn trong 90 ngày tới là gì?

Các ưu tiên theo quý. Không phải là khát vọng theo năm. Những việc mà nếu chưa làm xong vào tháng 7 thì bạn sẽ phải nói "tôi đã phí phạm quý 2".

```
1. [Ưu tiên 1]
2. [Ưu tiên 2]
3. [Ưu tiên 3]
```

---

## Câu 4 — Doanh thu thực sự đổ về đâu, và được theo dõi ở đâu?

Có thể trả lời nhiều nơi. Stripe? Skool? GoHighLevel? QuickBooks? Một file bảng tính?

```
[Câu trả lời của bạn ở đây]
```

---

## Câu 5 — Bạn nói chuyện với khách hàng, đội ngũ, và thế giới bên ngoài ở đâu mỗi ngày?

Email (email nào — Gmail / Outlook)? Slack? Teams? Tin nhắn riêng (Skool / Discord / iMessage)? Điện thoại?

```
[Câu trả lời của bạn ở đây]
```

---

## Câu 6 — Các bản ghi âm cuộc họp, ghi chú, và tài liệu quan trọng nằm ở đâu?

Granola? Otter? Fireflies? Google Drive? Notion? Dropbox? Một thư mục trên màn hình desktop mà bạn vẫn luôn định dọn dẹp?

```
[Câu trả lời của bạn ở đây]
```

---

## Câu 7 — Việc gì chiếm hết thời gian trong tuần của bạn, và bạn đang theo dõi công việc ở đâu?

Việc tốn thời gian nhất hoặc việc lặp đi lặp lại gây mệt mỏi nhất. Cùng với nơi các việc cần làm/dự án được theo dõi (ClickUp / Asana / Linear / Notion / một cuốn sổ tay).

```
[Câu trả lời của bạn ở đây]
```

---

Khi file này đã được điền đầy đủ, hãy chạy `/khoi-dong` (hoặc chạy lại) và trình thiết lập sẽ dựng bộ file Ngày-1 cho bạn: `context/`, `references/voice.md`, file `ket-noi.md` đã điền sẵn, và một file `CLAUDE.md` đã hoàn chỉnh.
