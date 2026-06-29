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

## Tabs dự kiến thêm mới (Giai đoạn 2)
| Tab | Mục đích | Cấu trúc dự kiến |
|-----|----------|-----------------|
| GA4_Web | Lưu sessions Web theo ngày | Ngày \| Sessions |
| GA4_App | Lưu sessions App theo ngày | Ngày \| Sessions |

---

## Lưu ý chung
- Tất cả date matching trong GAS dùng timestamp comparison (normalizeDate)
- Không dùng string compare vì Google Sheets có thể lưu Date kèm giờ phút giây
- Khi thêm cột mới: cập nhật file này trước khi sửa script