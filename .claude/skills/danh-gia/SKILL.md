---
name: danh-gia
description: Dùng khi ai đó yêu cầu đánh giá (audit) AIOS, yêu cầu chấm điểm thiết lập của họ theo Bốn chữ C, hoặc nói "đánh giá giúp tôi hệ thống này" / "AIOS của tôi có đang chạy tốt không" / "kiểm tra giúp tôi setup này" / "tìm các điểm thiếu trong AIOS của tôi". Tạo ra một bảng điểm Bốn-chữ-C kèm top 3 việc cần sửa, xếp theo mức độ ảnh hưởng (leverage).
---

## Kỹ năng này làm gì

Chạy **Đánh giá Bốn chữ C (Four Cs Audit)** trên project Claude Code hiện tại. Chỉ đọc (không bao giờ ghi/sửa) cẩm nang vận hành, bộ nhớ (memory), các kỹ năng, agent, MCP, quyết định, và tài liệu tham khảo của project. Chấm điểm mỗi chữ C trên thang 25 điểm. Nêu ra điểm mạnh và top 3 điểm thiếu có ảnh hưởng lớn nhất, kèm lệnh hành động cụ thể cho bước tiếp theo.

**Phạm vi mang tính cấu trúc — "AIOS đã được xây đúng cách chưa?"** Đây KHÔNG phải là một công cụ lập kế hoạch năng lực (capability planner). Các điểm thiếu về năng lực ("bạn có thể xây một bản tóm tắt hàng ngày nếu kết nối lịch") thuộc về `/nang-cap`. Đánh giá chỉ trả lời câu hỏi: các file, thư mục, danh sách đăng ký, và kết nối có đang ở trạng thái tốt không?

Lần chạy đầu tiên là cơ sở (baseline). Chạy lại hàng tuần để theo dõi điểm số tăng dần. Đó chính là "móc câu" tạo hiệu ứng tích lũy.

## Bối cảnh hôm nay

- **Ngày:** !`date +%Y-%m-%d`
- **Thư mục gốc project:** thư mục làm việc hiện tại

## Bốn chữ C (mỗi chữ chấm 25 điểm = tổng 100)

| Tầng | Bài kiểm tra |
|---|---|
| **Context** (Bối cảnh) | Hiểu doanh nghiệp — danh tính, đội ngũ, văn phong, quyết định, tài liệu tham khảo |
| **Connections** (Kết nối) | Truy cập được dữ liệu của người dùng — MCP, tích hợp, nguồn dữ liệu |
| **Capabilities** (Năng lực) | Biết cách thực hiện công việc — kỹ năng (skills) + agent |
| **Cadence** (Nhịp độ tự vận hành) | Tự chạy mà không cần được yêu cầu — lịch trình, hook, nghi thức lặp lại |

## Thực hiện

### Bước 1: Khám phá hình dạng của project

Quá trình đánh giá tìm **các khuôn mẫu và chủ đích**, không phải các đường dẫn chính xác. Tên file có thể khác nhau. Dùng Glob và Read để kiểm tra:

**Cẩm nang vận hành:** `CLAUDE.md` (gốc), `CLAUDE.local.md` (đã gitignore).
**Bộ nhớ (Memory):** `MEMORY.md` (gốc), `~/.claude/projects/<id>/memory/MEMORY.md`, hoặc thư mục `memory/`.
**Kỹ năng (Skills):** `.claude/skills/*/SKILL.md` — đếm số lượng + đọc frontmatter.
**Agent:** `.claude/agents/*.md` — đếm số lượng + đọc frontmatter.
**Cơ chế kết nối** (bất kỳ cái nào trong số này = "có thể truy cập được"):
- MCP: `.mcp.json`, `.claude/settings.json` (khoá mcpServers), `.claude/settings.local.json`
- Script gọi API: `scripts/*.py|.js|.ts` được ghi chú trong CLAUDE.md
- Pipeline xuất dữ liệu: thư mục `data/`, `imports/`, `exports/` kèm script làm mới + thời gian chạy lần cuối
- Khoá API + tài liệu hướng dẫn: các mục trong `.env` + file `references/{tool}-api.md` tương ứng

**Danh sách kết nối:** `ket-noi.md` (ở bất kỳ đâu).
**Tài liệu tham khảo:** `references/{tool}-api.md`, `references/*-reference.md`, hoặc tương đương.
**Quyết định:** `quyet-dinh/nhat-ky.md`, `quyet-dinh/nhat-ky.md`, hoặc bất kỳ file quyết định chỉ-thêm-không-xoá nào.
**Tài liệu tham khảo / Quy trình chuẩn (SOP):** thư mục `references/`, `docs/`, `sops/`.
**Mẫu (Templates):** `templates/`, `.claude/templates/`.
**Hook / công việc theo lịch:** khoá hooks trong `.claude/settings.json`, hoặc tên kỹ năng khớp với `morning-*`, `weekly-*`, `daily-*`, `monthly-*`, `standup`.

Đừng trừ điểm vì dùng tên không theo chuẩn, nếu chủ đích tương đương đã được thể hiện ở nơi khác.

### Bước 2: Chấm điểm mỗi chữ C (25 điểm mỗi chữ)

#### Context (25 điểm)

| Tiêu chí | Điểm | Cách phát hiện |
|---|---|---|
| Cẩm nang vận hành tồn tại và có nội dung thực chất (>200 từ) | 5 | Đọc CLAUDE.md, đếm số từ |
| Đã nắm được danh tính / vai trò / văn phong | 5 | CLAUDE.md có nhắc đến người dùng là ai + vai trò/sứ mệnh, HOẶC tồn tại `.claude/rules/*.md` |
| Bộ nhớ lâu dài tồn tại với nhiều mục | 5 | MEMORY.md tồn tại với >3 mục, HOẶC thư mục `memory/` có >3 file |
| Tài liệu tham khảo tồn tại | 5 | `references/`, `docs/`, hoặc `sops/` có ≥1 file |
| Đã ghi lại quyết định | 5 | `quyet-dinh/nhat-ky.md` hoặc tương đương có ≥1 mục |

#### Connections (25 điểm) — theo nhóm dữ liệu (domain), không quan trọng cơ chế

Một kết nối được coi là "truy cập được" qua BẤT KỲ cơ chế nào: MCP, script, pipeline xuất dữ liệu, hoặc khoá `.env` + `references/{tool}-api.md`. Bộ kit ưu tiên API trước; việc đánh giá không ưu ái MCP hơn các cơ chế khác.

**7 Nhóm Dữ liệu Phổ quát Bậc 1 (Tier-1):**

| # | Nhóm | Ví dụ |
|---|---|---|
| 1 | Doanh thu / Tài chính | Stripe, Skool, GoHighLevel, QuickBooks, Looker |
| 2 | Tương tác với khách hàng | HubSpot, Salesforce, Gmail-dùng-như-CRM, tin nhắn Skool |
| 3 | Lịch (Calendar) | Google Cal, Outlook, Calendly |
| 4 | Giao tiếp | Gmail, Outlook, Slack, Teams |
| 5 | Theo dõi dự án / công việc | ClickUp, Asana, Linear, Notion DB, Jira |
| 6 | Thông tin từ cuộc họp | Granola, Otter, Fireflies, Gong, Zoom |
| 7 | Kiến thức / tài liệu | Notion, Drive, Dropbox, Confluence, SharePoint |

**Bậc 2 (Tier-2, điểm cộng):** khoá API dịch vụ AI (OpenRouter, Anthropic, OpenAI), quyết định/lịch sử, nội dung/xuất bản.

| Tiêu chí | Điểm | Cách phát hiện |
|---|---|---|
| Độ phủ các nhóm Bậc-1 | 10 | 1.4 điểm cho mỗi nhóm bậc-1 truy cập được. Làm tròn đến 0.5. Tối đa 10. |
| Có tài liệu hướng dẫn | 5 | -1 điểm cho mỗi công cụ đã kết nối nhưng không có `references/{tool}-api.md`. Tối thiểu 0. |
| Độ "tươi mới" của xác thực / pipeline | 5 | -1 điểm cho mỗi kết nối ở trạng thái `needs-auth`/`expired`, hoặc script chưa chạy trong 30 ngày. Tối thiểu 0. |
| Có ghi chép trong `ket-noi.md` | 3 | 0 nếu thiếu; 1 nếu sơ sài; 2 nếu hầu hết; 3 nếu phủ đủ mọi kết nối đang truy cập được. |
| Cân bằng giữa đọc và viết | 2 | Có ít nhất một kết nối có thể VIẾT (gửi email, đăng cập nhật, v.v.). 0 nếu tất cả chỉ-đọc — AIOS chỉ là một công cụ xem, không phải một hệ điều hành thực sự. |

#### Capabilities (25 điểm)

| Tiêu chí | Điểm | Cách phát hiện |
|---|---|---|
| Có từ 3 kỹ năng trở lên | 10 | Đếm `.claude/skills/*/SKILL.md` |
| Có từ 1 kỹ năng do người dùng tự xây | 10 | Tên kỹ năng không thuộc nhóm: `khoi-tao`, `danh-gia`, `nang-cap`, `skill-creator`, `skill-builder`, `decision`, `connect`, `connect-check`, `memory-prune`, `scaffold-skill`, `scaffold-agent`, `draft`, `standup` (các kỹ năng có sẵn từ AIS-OS + Anthropic) |
| Có ít nhất 1 agent | 5 | Đếm `.claude/agents/*.md` ≥ 1 |

#### Cadence (25 điểm)

| Tiêu chí | Điểm | Cách phát hiện |
|---|---|---|
| Có từ 1 kích hoạt định kỳ/theo lịch | 10 | hooks trong `.claude/settings.json`, HOẶC tên kỹ năng khớp `morning-*` / `daily-*` / `weekly-*` / `monthly-*` / `standup` |
| Có dấu hiệu hoạt động/sử dụng gần đây | 10 | File trong `.claude/skills/` được sửa trong 30 ngày qua, HOẶC `quyet-dinh/nhat-ky.md` có mục trong 30 ngày qua |
| Thư mục mẫu (templates) đã có nội dung | 5 | `templates/` hoặc `.claude/templates/` có ≥1 file |

### Bước 3: Xác định top 3 điểm thiếu theo mức độ ảnh hưởng (leverage)

Với mỗi tiêu chí bị mất điểm: mức ảnh hưởng = (số điểm mất) × (hệ số tác động).

**Các hệ số tác động:**
- 0 nhóm bậc-1 truy cập được: **4x** (AIOS hoàn toàn "mù" với doanh nghiệp)
- Cẩm nang vận hành thiếu hoặc quá sơ sài: **3x** (đây là nền tảng)
- ≤2 nhóm bậc-1 truy cập được: **3x** (Connections là cổng vào dữ liệu thực)
- 0 kỹ năng: **2x** (không có Capabilities = không có AIOS)
- Không có kích hoạt định kỳ: **2x** (không có Cadence = không có tính tự chủ)
- Mọi kết nối đều chỉ-đọc: **2x** (chỉ là công cụ xem, không phải hệ điều hành)
- 0 tài liệu hướng dẫn cho các công cụ đã kết nối: **1.5x** (mỗi kỹ năng tương lai sẽ phải nghiên cứu lại cùng một API)
- Không có nhật ký quyết định: **1.5x**
- Tất cả các trường hợp khác: **1x**

Sắp xếp các điểm thiếu theo mức ảnh hưởng giảm dần. Lấy top 3. Với mỗi điểm, viết một bước hành động cụ thể, một dòng:
- **Cần một kỹ năng mới?** Gợi ý `skill-creator` (của Anthropic) hoặc `skill-builder` (nếu có sẵn cục bộ), hoặc "viết SKILL.md tại `.claude/skills/<tên>/SKILL.md` kèm frontmatter YAML."
- **Cần ghi lại một quyết định?** "Thêm vào cuối `quyet-dinh/nhat-ky.md`."
- **Cần kết nối tới một nhóm bậc-1?** Ưu tiên API+script (viết `scripts/{tool}_api.py` + lưu `references/{tool}-api.md`). Chỉ gợi ý `claude mcp add` nếu không có cách nào qua API.
- **Công cụ đã kết nối nhưng thiếu tài liệu hướng dẫn?** "Nghiên cứu API một lần, lưu endpoint + cách xác thực + các truy vấn thường dùng vào `references/{tool}-api.md`."
- **Cần một kích hoạt định kỳ?** "Thêm một hook vào `.claude/settings.json`, hoặc viết một kỹ năng tên `daily-*` mà bạn chạy mỗi sáng."

### Bước 4: Xuất báo cáo

In trực tiếp trong khung chat (định dạng Markdown). Mẫu:

```
# Đánh giá AIOS (AIOS Audit) — {date}
**Điểm: {total}/100** ({stage})

Các mức ngưỡng:
- 0-39 → Mức 0: Nền tảng (Foundation)
- 40-69 → Mức 1: Đã xây dựng (Built)
- 70-89 → Mức 2: Tích luỹ (Compounding)
- 90-100 → Mức 3: Tự chủ (Autonomous)

## Bảng điểm

Context        {bar}  {n}/25  {label}
Connections    {bar}  {n}/25  {label}
Capabilities   {bar}  {n}/25  {label}
Cadence        {bar}  {n}/25  {label}

(bar = ## cho mỗi 5 điểm; label = "Mạnh" (Strong) ≥20, "Tốt" (Solid) 15-19, "Mỏng" (Thin) 8-14, "Thiếu" (Missing) <8)

## Điểm mạnh
- {1-3 gạch đầu dòng ngắn từ các tiêu chí đạt điểm cao nhất}

## Top 3 điểm thiếu (xếp theo mức ảnh hưởng)
1. **{tên điểm thiếu}** (-{điểm} × {hệ số})
   → {bước hành động cụ thể}
2. **{tên điểm thiếu}** (-{điểm} × {hệ số})
   → {bước hành động cụ thể}
3. **{tên điểm thiếu}** (-{điểm} × {hệ số})
   → {bước hành động cụ thể}

## Gợi ý hành động tiếp theo: {hành động có ảnh hưởng lớn nhất}

---
Đây chỉ là các điểm thiếu về cấu trúc. Để khám phá các điểm thiếu về NĂNG LỰC (những gì AIOS của bạn có thể LÀM mà hiện chưa làm được), hãy chạy /nang-cap sau khi đánh giá này xong.
```

### Bước 5: Đề xuất lưu báo cáo

Sau khi in ra, hỏi: "Lưu báo cáo đánh giá này vào `danh-gia/danh-gia-{date}.md` để bạn theo dõi điểm số theo thời gian không?" Nếu đồng ý, ghi file (tạo thư mục `danh-gia/` nếu cần). Đây là tác động ghi-file duy nhất có thể xảy ra (và chỉ khi được đồng ý).

## Lưu ý

- **Chỉ đọc theo mặc định.** Không bao giờ sửa CLAUDE.md, memory, skills, hoặc bất kỳ file project nào. Tác động ghi duy nhất (tuỳ chọn) là báo cáo đánh giá.
- **Linh hoạt về tên file.** Không trừ điểm vì dùng tên không theo chuẩn nếu chủ đích đã được thể hiện.
- **Trung thực, không nuông chiều.** 95/100 là một lời khen lớn. Hầu hết các thiết lập rơi vào khoảng 40-70.
- **Không gợi ý các kỹ năng không tồn tại.** Chỉ chỉ vào những gì thực sự có sẵn.
- **Tốc độ quan trọng.** Báo cáo trong dưới 60 giây thực tế. Đọc các file mục tiêu, đếm thư mục kỹ năng mà không cần đọc hết toàn bộ mỗi file (chỉ cần đọc frontmatter).
- **Việc phát hiện Cadence mang tính ước lượng.** Suy luận từ tên kỹ năng nếu không có sẵn dữ liệu hook/cron rõ ràng.
