# TARGET Sheet — Schema Chi Tiết

## File ID
1jwsqkf5v0qHyNmMi-8Meo4JN6Y4xyTO4eLtWmAN_CDU

---

## Tab: Online
| Cột | Header | Ghi chú |
|-----|--------|---------|
| A | Ngày | Date object, format dd/MM/yyyy |
| B | Doanh thu | Số thực đạt hàng ngày |
| C | Đơn hàng | Số thực đạt hàng ngày |
| D | Lãi gộp | Số thực đạt hàng ngày |
| E | Target DT | Ghi 1 lần vào ngày 01/MM — GAS T2 |
| F | Target LG | Ghi 1 lần vào ngày 01/MM — GAS T2 |

---

## Tab: WEB
| Cột | Header | Ghi chú |
|-----|--------|---------|
| A | Ngày | Date object |
| B | Doanh thu | GAS T1 ghi hàng ngày |
| C | Đơn hàng | GAS T1 ghi hàng ngày |
| D | Loại kênh | Luôn = "WEB" — dùng cho Data Studio filter |
| E | Target DT | GAS T4 ghi ngày 01/MM |
| F | Target ĐH | GAS T4 ghi ngày 01/MM |
| G | Target AOV | GAS T4 ghi ngày 01/MM |
| H | Target CR | GAS T4 ghi ngày 01/MM |
| I | Target Traffic | GAS T4 ghi ngày 01/MM |

---

## Tab: APP
Cấu trúc giống hệt tab WEB.
Cột D luôn = "APP".

---

## Tab: Sàn
| Cột | Header | Ghi chú |
|-----|--------|---------|
| A | Ngày | Date object |
| B | DT tổng | Không dùng trong GAS hiện tại — dùng cho Data Studio |
| C | ĐH tổng | Không dùng trong GAS hiện tại — dùng cho Data Studio |
| D | Loại kênh | Luôn = "Sàn" |
| E | Target DT | GAS T4 ghi ngày 01/MM |
| F | Target ĐH | GAS T4 ghi ngày 01/MM |
| G | Target AOV | GAS T4 ghi ngày 01/MM |
| H | (Trống) | Reserved |
| I | DT Shopee | GAS T1 ghi hàng ngày |
| J | DT MWG (Tintin) | GAS T1 ghi hàng ngày |
| K | ĐH Shopee | GAS T1 ghi hàng ngày |
| L | ĐH MWG (Tintin) | GAS T1 ghi hàng ngày |

---

## Tab: Affiliate
| Cột | Header | Ghi chú |
|-----|--------|---------|
| A | Ngày | Date object |
| B | Doanh thu | GAS T1 ghi hàng ngày |
| C | Đơn hàng | GAS T1 ghi hàng ngày |
| D | Loại kênh | Luôn = "Affiliate" |
| E | Target DT | GAS T4 ghi ngày 01/MM |
| F | Target ĐH | GAS T4 ghi ngày 01/MM |
| G | Target AOV | GAS T4 ghi ngày 01/MM |

---

## Tab: CC
| Cột | Header | Ghi chú |
|-----|--------|---------|
| A | Ngày | Date object |
| B | Doanh thu | Nhập thủ công hoặc nguồn khác |
| C | Đơn hàng | Nhập thủ công hoặc nguồn khác |
| D | Loại kênh | Luôn = "CC" |

> CC = Online tổng trừ (Web + App + Sàn + Affiliate) — tự tính trong sheet, GAS không ghi trực tiếp.

---

## Tab: Danh mục
| Cột | Header | Ghi chú |
|-----|--------|---------|
| A | Ngày | Luôn = ngày 01/MM (đại diện cả tháng) |
| B | Ngành hàng | Tên danh mục sản phẩm |
| C | Doanh thu | Lũy kế cả tháng — GAS T3 ghi hàng ngày (overwrite) |

> Mỗi tháng sẽ có N rows tương ứng N danh mục, tất cả cùng ngày 01/MM.

---

## Tab: GA4_Web
| Cột | Header | Ghi chú |
|-----|--------|---------|
| A | Ngày | Date object |
| B | Sessions | GAS T5 ghi hàng ngày (lookback 3 ngày) |

> Sessions hệ sản phẩm = Tổng sessions - Sessions excluded (landing page blog/bệnh/hoạt chất).
> Excluded regex: `(^/ban-tin-suc-khoe.*)|(^/hoat-chat.*)|(^/benh.*)|(^/trieu-chung.*)`.
> Sai số ~vài trăm đến 1k sessions/ngày so với GA4 UI — chấp nhận được, mục tiêu là theo dõi CR trend.
> GA4 Property ID Web: 319910173.

---

## Tab: GA4_App
| Cột | Header | Ghi chú |
|-----|--------|---------|
| A | Ngày | Date object |
| B | Sessions | GAS T5 ghi hàng ngày (lookback 3 ngày) |

> Không filter landing page (App không có khái niệm landing page).
> GA4 Property ID App: 500599006.

---

## Tab: Nhận định
| Cột | Header | Ghi chú |
|-----|--------|---------|
| A | Ngày | Date object, ngày 01/MM đại diện cả tháng |
| B | Slide | Số slide (1, 2, hoặc 3) |
| C | Nội dung | Văn bản nhận định — PM nhập tay |

> PM nhập trực tiếp vào sheet. Dashboard đọc và hiển thị tự động — không có UI chỉnh sửa trên dashboard.

---

## Tab: Dự án
| Cột | Header | Ghi chú |
|-----|--------|---------|
| A | Tháng | Date object, ngày 01/MM đại diện cả tháng |
| B | Loại | "done" (đã xong tháng này) hoặc "plan" (kế hoạch tháng tới) |
| C | STT | Số thứ tự hiển thị trong dashboard |
| D | Tên dự án | Tên task/dự án |
| E | Tag | "Doanh thu" / "Traffic" / "Thuận tiện" — hoặc để trống |
| F | Timeline | Ngày dự kiến go live, VD: "22/05" — hoặc để trống |

> Loại khác "done"/"plan" → bỏ qua, không lỗi.
> Tag mới ngoài 3 loại trên → hiển thị màu xám mặc định, không lỗi.
> Cột F hỗ trợ cả Date object lẫn string.

---

## Lưu ý chung
- Tất cả date matching trong GAS dùng timestamp comparison (normalizeDate)
- Không dùng string compare vì Google Sheets có thể lưu Date kèm giờ phút giây
- Khi thêm cột mới: cập nhật file này trước khi sửa script
- getReportData() đọc tất cả tabs trong 1 batch operation để tối ưu tốc độ
