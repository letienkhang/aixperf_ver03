# AIxPerf

MVP giao diện quản lý KPI: màn hình chính và wizard tạo KPI (popup).

## Chạy local

Mở file `index.html` trực tiếp trong trình duyệt, hoặc dùng server tĩnh:

```bash
# Python 3
python3 -m http.server 8000

# Node (npx)
npx serve .
```

Sau đó mở http://localhost:8000 (hoặc cổng tương ứng).

## Tính năng MVP

- **Màn hình chính**: Nút **Tạo KPI**
- **Popup wizard**: Bước 1 (Thông tin chung), Bước 2 (Phạm vi & Thời gian)
  - Phạm vi: Toàn công ty / Bộ phận / Cá nhân
  - Năm áp dụng: 2023–2026
  - Nút Đóng, Quay lại, Xác nhận

## Design System

- **`design-system.css`**: biến màu, border, nền (vàng cam — border đậm, nền nhạt + opacity).
- **`UI_GUIDELINES.md`**: quy ước UI; mỗi lần build phải tuân thủ file này.

## Công nghệ

- HTML5, Tailwind CSS (CDN), Material Symbols, Inter font.
