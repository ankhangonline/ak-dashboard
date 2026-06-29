# An Khang Dashboard — Project Brief

## Tổng quan
PM: Đức Anh
Mảng: Online Nhà thuốc An Khang (kênh bán lẻ dược mỹ phẩm online, thuộc MWG)
Mục tiêu: Tự động hóa theo dõi sức khỏe web/app/online

## Luồng 1: Daily Dashboard (ĐÃ XONG)
SOURCE → [GAS T1-T4] → TARGET → Data Studio

## Luồng 2: Monthly Report (ĐÃ XONG)
TARGET + GA4 → [GAS API] → HTML Report → GitHub Pages URL

## Files & IDs
- SOURCE sheet ID: 1ImPVNq7v2eebQDzSmbCdE5Uho8q76X16H90LMo1f_qM
- TARGET sheet ID: 1jwsqkf5v0qHyNmMi-8Meo4JN6Y4xyTO4eLtWmAN_CDU
- PLANNING sheet ID: 1RyO1Ss10LiQVRgIFOLwOKznK_kqjyjmPXsfPb6-gZJI
- APP DOWNLOADS sheet ID: 1XQXPFbpD5DfBay-ESpJbtdqRopB0eWnky1MmSgTneFM
- GAS Web App URL: https://script.google.com/macros/s/AKfycbzJaaAxK9d3rUT3RNWaoFRsWOS-KbVZM7pkSG3CJxAxIOVX-8_kYDCe55EeeifVpEqUOQ/exec
- GitHub Repo: https://github.com/ankhangonline/ak-dashboard
- Dashboard URL: https://ankhangonline.github.io/ak-dashboard/

## GAS Script
- File: master_robot.gs (version hiện tại: V18.0)
- Entry point: run_Master_System_Ultimate()
- Lập lịch: 2 lần/ngày (9:00–10:00 và 15:00–16:00)
- T2 và T4 chỉ chạy ngày 01/tháng (hoặc khi FORCE_TARGET_MONTHS = ["ALL"])

## TARGET Sheet — Cấu trúc tabs
- Online: Ngày | DT | ĐH | LN | Target DT | Target LG
- WEB: Ngày | DT | ĐH | Loại | Target DT | Target DH | Target AOV | Target CR | Target traffic
- APP: (cấu trúc giống WEB)
- Sàn: Ngày | DT | ĐH | Loại | Target DT | Target DH | Target AOV | (H trống) | DT Shopee | DT MWG | ĐH Shopee | ĐH MWG
- Affiliate: (cấu trúc giống Sàn, không có cột H trở đi)
- CC: Ngày | DT | ĐH | Loại (tự tính trong sheet, GAS không ghi)
- Danh mục: Ngày | Ngành hàng | Doanh thu
- GA4_Web: Ngày | Sessions (GAS T5, Web Property 319910173)
- GA4_App: Ngày | Sessions (GAS T5, App Property 500599006)
- Nhận định: Ngày | Slide | Nội dung (PM nhập tay)
- Dự án: Tháng | Loại | STT | Tên dự án | Tag | Timeline (PM nhập tay)

## Vấn đề đã biết trong script hiện tại
1. Có 2 hàm trùng tên safeSync và safeSyncSanOnly — GAS dùng bản cuối (không ảnh hưởng hoạt động)
2. T1 đọc từng cell riêng lẻ thay vì batch — chậm hơn nhưng không gây lỗi
3. GA4 Web sessions dùng công thức (tổng - excluded), sai số ~vài trăm đến 1k/ngày so với GA4 UI — chấp nhận được vì mục tiêu là theo dõi CR trend

## Báo cáo Monthly — 3 slides
- Slide 1: Tổng quan Online (DT tháng hiện tại vs tháng trước, theo ngành hàng, theo kênh)
- Slide 2: Sức khỏe Web-App (DT, Sessions, CR, Lượt giữ app)
- Slide 3: Dự án lớn done/plan (đọc từ tab "Dự án" trong TARGET Sheet)

## Quyết định kỹ thuật đã chốt
- Version control: GitHub (repo: ankhangonline/ak-dashboard)
- Hosting báo cáo: GitHub Pages + password bảo vệ (SHA-256)
- GA4: lấy sessions theo ngày cho cả Web và App, lookback 3 ngày
- Slide 3: đọc từ tab "Dự án" trong TARGET Sheet — PM nhập tay, không edit qua UI dashboard
- Nhận định: đọc từ tab "Nhận định" trong TARGET Sheet — PM nhập tay
- Dashboard chỉ hiển thị các tháng đã qua (ẩn tháng hiện tại)
- Khi thêm tháng mới: cập nhật mảng MONTHS trong docs/index.html
