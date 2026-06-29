# An Khang Online — Dashboard Sức Khỏe Kinh Doanh

Hệ thống tự động hóa theo dõi và báo cáo sức khỏe kinh doanh Online hàng tháng của Nhà thuốc An Khang (thuộc MWG).

---

## 🔗 Link truy cập

| Tài nguyên | Link |
|---|---|
| **Dashboard** | https://ankhangonline.github.io/ak-dashboard/ |
| SOURCE Sheet | https://docs.google.com/spreadsheets/d/1ImPVNq7v2eebQDzSmbCdE5Uho8q76X16H90LMo1f_qM |
| TARGET Sheet (Kho + GAS) | https://docs.google.com/spreadsheets/d/1jwsqkf5v0qHyNmMi-8Meo4JN6Y4xyTO4eLtWmAN_CDU |
| PLANNING Sheet | https://docs.google.com/spreadsheets/d/1RyO1Ss10LiQVRgIFOLwOKznK_kqjyjmPXsfPb6-gZJI |
| APP DOWNLOADS Sheet | https://docs.google.com/spreadsheets/d/1XQXPFbpD5DfBay-ESpJbtdqRopB0eWnky1MmSgTneFM |

> Mật khẩu dashboard và quyền truy cập GitHub: liên hệ PM hiện tại.

---

## 📁 Cấu trúc repo

```
ak-dashboard/
├── docs/
│   └── index.html        # File HTML dashboard đang chạy live
├── GAS.txt               # GAS script mới nhất (master_robot v18)
├── PROJECT_BRIEF.md      # Tổng quan dự án, IDs, quyết định kỹ thuật
├── TARGET_SCHEMA.md      # Cấu trúc chi tiết từng tab trong TARGET Sheet
└── README.md             # File này
```

---

## ⚙️ Hệ thống hoạt động như thế nào

```
SOURCE Sheet ──┐
PLANNING Sheet ─┼── GAS (T1–T5, chạy 2 lần/ngày) ──► TARGET Sheet ──► Dashboard (GitHub Pages)
APP Downloads ──┤
GA4 API ────────┘
```

GAS chạy tự động **2 lần/ngày** (9:00–10:00 và 15:00–16:00). PM không cần làm gì ngoài kiểm tra kết quả và viết nhận định cuối tháng.

---

## 📋 Việc PM cần làm hàng tháng

**Đầu tháng (ngày 01):**
- Kiểm tra TARGET Sheet có target tháng mới chưa (tab Online cột E, F)
- Nếu thiếu: mở GAS → chạy tay `run_Master_System_Ultimate`

**Cuối tháng (trước ngày báo cáo):**
- Mở TARGET Sheet → tab **Nhận định** → điền nhận định cho 3 slides
- Mở TARGET Sheet → tab **Dự án** → cập nhật danh sách done/plan

**Khi sang năm hoặc thêm tháng mới:**
- Mở `docs/index.html` → tìm `const MONTHS = [...]` → thêm tháng mới vào cuối

---

## 📖 Tài liệu chi tiết

Xem **[Hướng dẫn vận hành](https://docs.google.com/document/d/1OJ1A4aYU8jgNkH0QMjU8cUW0sSGI6VnA7mtozr40bts)** để biết đầy đủ quy trình, xử lý lỗi và liên hệ hỗ trợ.

---

*PM Team Online · Nhà thuốc An Khang · Cập nhật tháng 6/2026*
