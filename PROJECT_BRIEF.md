# An Khang Dashboard — Project Brief

## Tổng quan
PM: Đức Anh
Mảng: Online Nhà thuốc An Khang (kênh bán lẻ dược mỹ phẩm online, thuộc MWG)
Mục tiêu: Tự động hóa theo dõi sức khỏe web/app/online

## Luồng 1: Daily Dashboard (ĐÃ XONG)
SOURCE → [GAS T1-T4] → TARGET → Data Studio

## Luồng 2: Monthly Report (ĐANG LÀM)
TARGET + GA4 → [GAS API] → HTML Report → GitHub Pages URL

## Files & IDs
- SOURCE sheet ID: 1ImPVNq7v2eebQDzSmbCdE5Uho8q76X16H90LMo1f_qM
- TARGET sheet ID: 1jwsqkf5v0qHyNmMi-8Meo4JN6Y4xyTO4eLtWmAN_CDU
- PLANNING sheet ID: 1RyO1Ss10LiQVRgIFOLwOKznK_kqjyjmPXsfPb6-gZJI
- APP DOWNLOADS sheet ID: 1XQXPFbpD5DfBay-ESpJbtdqRopB0eWnky1MmSgTneFM
- GAS Web App URL: https://script.google.com/macros/s/AKfycbz.../exec

## TARGET Sheet — Cấu trúc tabs
- Online: Ngày | DT | ĐH | LN | Target DT | Target LG
- WEB: Ngày | DT | ĐH | Loại | Target DT | Target DH | Target AOV | Target CR | Target traffic
- APP: (cấu trúc giống WEB)
- Sàn: Ngày | DT | ĐH | Loại | Target DT | Target DH | Target AOV
- Affiliate: (cấu trúc giống Sàn)
- CC: Ngày | DT | ĐH | Loại
- Danh mục: Ngày | Ngành hàng | Doanh thu

## Vấn đề đã biết trong script hiện tại
1. Có 2 hàm trùng tên safeSync và safeSyncSanOnly — GAS dùng bản cuối
2. T1 đọc từng cell riêng lẻ thay vì batch — chậm nhưng không gây lỗi
3. GA4 chưa tích hợp — sessions chưa có trong báo cáo
4. GA4 Web sessions lấy theo công thức (tổng - excluded), sai số ~vài trăm đến 1k/ngày so với GA4 UI do data thresholding và (not set) rows. Acceptable vì mục tiêu là CR trend.

## Báo cáo Monthly — 3 slides
- Slide 1: Tổng quan Online (DT tháng hiện tại vs tháng trước, theo ngành hàng, theo kênh)
- Slide 2: Sức khỏe Web-App (DT, Sessions, CR, Lượt tải)
- Slide 3: Việc đã làm & kế hoạch (nhập tay)

## Quyết định kỹ thuật đã chốt
- Version control: GitHub
- Hosting báo cáo: GitHub Pages + simple password
- GA4: lấy sessions theo ngày cho cả Web và App
- Slide 3: nhập tay, chừa room để tự động hóa sau
