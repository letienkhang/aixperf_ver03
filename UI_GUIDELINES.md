# Điều khoản UI — AIxPerf Design System

Mỗi lần build giao diện **bắt buộc** dùng file `design-system.css` và tuân thủ các quy ước dưới đây.

---

## 1. Màu sắc

### 1.1 Màu chủ đạo: Vàng (#ffc84a)
- **Primary**: `#ffc84a` — nút chính, trạng thái active, link.
- **Primary hover**: `#e6b43d`.
- **Primary light**: vàng nhạt + opacity — nền highlight, vùng được chọn.

### 1.2 Viền đậm / Nền nhợt nhợt (opacity)
- **Viền (border) đậm**: `#ffc84a` (`--border`, `--border-strong`), độ dày tối thiểu **2px**.
- **Nền (surface)** — nhợt nhợt, dùng opacity:
  - `--surface`: `rgba(255, 200, 74, 0.18)` (nền vàng nhạt opacity).
  - `--surface-solid`: nền vàng rất nhạt, có opacity.
- **Border nhạt** (phân cách): `--border-light`.

### 1.3 Chữ
- Chữ chính: `--text-main` (#1C1917).
- Chữ phụ: `--text-secondary` (#78716C).
- Chữ trên nền primary: `--text-on-primary` (tối cho dễ đọc).

### 1.4 Nền trang
- Nền trang: `--bg-page` (vàng nhạt opacity).

---

## 2. Viền (Border)

- Card, modal, input, vùng nổi: **border đậm** (màu `--border` hoặc `--border-strong`), **2px**.
- Có thể dùng `ds-border` / `ds-border-strong` từ `design-system.css`.

---

## 3. Nền (Background)

- Vùng nội dung chính (card, popup, panel): **bg nhợt nhợt + opacity** (`--surface`) hoặc `--surface-solid`.
- Tránh nền trắng thuần (#fff) cho các khối chính.

---

## 4. File base

- **`design-system.css`**: chứa toàn bộ biến CSS (tokens). Mọi trang/component cần link file này và ưu tiên dùng biến thay vì màu hard-code.
- Khi thêm token mới: thêm vào `design-system.css` và (nếu cần) cập nhật mục tương ứng trong file này.

---

## 5. Checklist khi build

- [ ] Đã link `design-system.css`.
- [ ] Nền card/modal/panel dùng `--surface` hoặc `--surface-solid`, không dùng #fff.
- [ ] Viền đậm (2px) dùng `--border` / `--border-strong`.
- [ ] Nút chính, active state dùng `--primary` / `--primary-hover`.
- [ ] Shadow (nếu có) dùng `--shadow-primary` cho đồng bộ.
