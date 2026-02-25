# UI Guidelines — AIxPerf

**Quy ước UI cho mọi lần tạo giao diện.** Mỗi lần build UI **bắt buộc** tuân thủ file này và dùng `design-system.css`.

---

## 📋 Mục lục

1. [Layout Structure](#1-layout-structure)
2. [Màu sắc & Tokens](#2-màu-sắc--tokens)
3. [Typography](#3-typography)
4. [Components](#4-components)
5. [Spacing & Sizing](#5-spacing--sizing)
6. [Icons](#6-icons)
7. [States & Interactions](#7-states--interactions)
8. [Patterns](#8-patterns)
9. [Checklist](#9-checklist)

---

## 1. Layout Structure

### 1.1 Cấu trúc chính
```
<body class="min-h-screen bg-white flex">
  <nav>...</nav>          <!-- Cột nav trái, width: 240px (w-60) -->
  <div class="flex-1">    <!-- Nội dung bên phải -->
    <div class="panel">...</div>  <!-- Panel theo nav item -->
  </div>
</body>
```

### 1.2 Nav Sidebar
- **Width**: `w-60` (240px)
- **Background**: `bg-white`
- **Border**: `border-r` với `border-color: var(--border)`
- **Structure**:
  - Thanh trên cùng: `h-1` background `#1f2937`
  - Header: Logo + "AIxPerf" + nút thu gọn
  - Divider: đường nét đứt (`border-bottom: 1px dashed`)
  - Nav items: danh sách menu
  - Footer: User profile

### 1.3 Content Area
- **Flex-1**: chiếm phần còn lại
- **Panels**: mỗi nav item có một panel tương ứng
- **Panel active**: `class="panel"` (không hidden)
- **Panel inactive**: `class="panel hidden"`

---

## 2. Màu sắc & Tokens

### 2.1 Primary (Vàng)
- **`--primary`**: `#ffc84a` — chỉ dùng cho **button chính** (Tạo KPI, Tiếp theo, Xác nhận)
- **`--primary-hover`**: `#e6b43d` — hover của button primary
- **`--primary-light`**: `#f5f5f5` — nền highlight nhẹ (không phải vàng)

### 2.2 Border
- **`--border`**: `#e5e7eb` (xám nhạt) — dùng cho **tất cả** border (card, input, modal, divider)
- **`--border-strong`**: `#e5e7eb` — tương tự `--border`
- **`--border-light`**: `#f3f4f6` — phân cách nhẹ
- **`--border-button`**: `#ffc84a` — **chỉ** cho border của button primary

**Quy tắc**: Tất cả border đều xám nhạt, **trừ button primary** giữ vàng.

### 2.3 Background
- **`--surface`**: `#ffffff` (trắng)
- **`--surface-solid`**: `#ffffff` (trắng)
- **`--bg-page`**: `#ffffff` (trắng)

**Quy tắc**: Nền trắng cho tất cả (không dùng vàng nhạt).

### 2.4 Text
- **`--text-main`**: `#1C1917` — chữ chính
- **`--text-secondary`**: `#78716C` — chữ phụ, mô tả
- **`--text-on-primary`**: `#1C1917` — chữ trên nền button vàng

### 2.5 Shadow
- **`--shadow-primary`**: `rgba(255, 200, 74, 0.3)` — shadow cho button primary

---

## 3. Typography

### 3.1 Font Family
- **Font**: `'Inter', sans-serif`
- **Source**: Google Fonts (link trong `<head>`)

### 3.2 Font Sizes
- **Nav title "AIxPerf"**: `text-sm` (14px)
- **Nav items**: `font-size: 14px` (trong CSS `.nav-item`)
- **Heading h2**: `text-2xl` (24px)
- **Heading h3**: `text-lg` (18px)
- **Body**: mặc định (16px)
- **Small text**: `text-sm` (14px)
- **Extra small**: `text-xs` (12px)

### 3.3 Font Weights
- **Bold**: `font-bold` (700) — tiêu đề
- **Semibold**: `font-semibold` (600) — subheading, nav active
- **Medium**: `font-medium` (500) — nhấn mạnh
- **Regular**: mặc định (400) — body text

---

## 4. Components

### 4.1 Button Primary
```html
<button class="px-8 py-4 rounded-xl font-semibold shadow-lg border-2"
  style="background-color: var(--primary); color: var(--text-on-primary); 
         border-color: var(--border-button); 
         box-shadow: 0 10px 15px -3px var(--shadow-primary);">
  <span class="material-symbols-outlined text-2xl">add_circle</span>
  Tạo KPI
</button>
```
- **Background**: `var(--primary)` (#ffc84a)
- **Border**: `var(--border-button)` (#ffc84a), 2px
- **Hover**: `background-color: var(--primary-hover)`
- **Shadow**: `var(--shadow-primary)`

### 4.2 Button Secondary
```html
<button class="px-6 py-2.5 rounded-xl border-2 font-semibold"
  style="border-color: var(--border); color: var(--text-main);">
  Quay lại
</button>
```
- **Background**: transparent
- **Border**: `var(--border)` (xám), 2px
- **Hover**: `background-color: rgba(255,200,74,0.15)` (vàng nhạt)

### 4.3 Input / Select
```html
<input class="block w-full rounded-lg border-2 py-3 px-4"
  style="border-color: var(--border); background-color: var(--surface-solid); 
         color: #000;">
```
- **Border**: `var(--border)`, 2px
- **Background**: `var(--surface-solid)` (trắng)
- **Text color**: `#000` (đen)
- **Focus ring**: `focus:ring-2 focus:ring-[var(--primary)]` (vàng)

### 4.4 Card
```html
<div class="rounded-xl border-2 p-4"
  style="background-color: var(--surface-solid); border-color: var(--border);">
```
- **Border**: `var(--border)`, 2px
- **Background**: `var(--surface-solid)` (trắng)
- **Border radius**: `rounded-xl` (12px)

### 4.5 Nav Item
```html
<a href="#" class="nav-item active" style="color: var(--text-main);">
  <span class="material-symbols-outlined nav-icon">bar_chart</span>
  KPI
</a>
```
- **Font size**: `14px`
- **Icon size**: `18px`
- **Padding**: `12px 16px`
- **Active**: `background: rgba(0,0,0,0.06)` + `border-left: 3px solid var(--primary)`
- **Hover**: `background: rgba(0,0,0,0.04)`

### 4.6 Radio Card (Scope selection)
```html
<label class="cursor-pointer block">
  <input class="peer sr-only" type="radio" name="scope" value="company"/>
  <div class="p-3 rounded-xl border-2 flex items-center gap-3"
    style="border-color: var(--border-light);">
    <div class="w-5 h-5 rounded-full border-2"
      style="border-color: var(--border); background: var(--primary);">
      <div class="w-2.5 h-2.5 rounded-full bg-white"></div>
    </div>
    <div>
      <span class="font-semibold text-sm">Toàn bộ công ty</span>
      <span class="text-xs">Mô tả</span>
    </div>
  </div>
</label>
```
- **Checked state**: `border-color: var(--border-strong)`, `background-color: var(--primary-light)`
- **Radio dot**: `background: var(--primary)` khi checked

### 4.7 Year Pill
```html
<label class="cursor-pointer">
  <input class="peer sr-only" type="radio" name="year" value="2026"/>
  <div class="year-pill px-8 py-3 rounded-xl border-2 font-semibold text-sm"
    style="border-color: var(--border); background: var(--surface-solid);">
    2026
  </div>
</label>
```
- **Checked**: `background: var(--primary)`, `color: var(--text-on-primary)`, `border-color: var(--border)`

---

## 5. Spacing & Sizing

### 5.1 Padding
- **Nav item**: `12px 16px` (`py-3 px-4`)
- **Card content**: `p-4` (16px)
- **Form section**: `pt-4 px-10 pb-10`
- **Modal header**: `p-6`
- **Modal footer**: `p-6`

### 5.2 Gap
- **Nav icon + text**: `gap-2` (8px)
- **Card items**: `gap-3` (12px)
- **Form sections**: `space-y-3` hoặc `space-y-10`

### 5.3 Border Radius
- **Button**: `rounded-xl` (12px)
- **Card**: `rounded-xl` (12px)
- **Input**: `rounded-lg` (8px)
- **Icon container**: `rounded-lg` (8px)

### 5.4 Border Width
- **Tất cả**: `2px` (`border-2`)
- **Nav active indicator**: `3px` (`border-left: 3px`)

---

## 6. Icons

### 6.1 Material Symbols
- **Source**: Google Fonts Material Symbols Outlined
- **Size mặc định**: `text-xl` (20px)
- **Nav icons**: `18px` (`.nav-icon`)
- **Button icons**: `text-2xl` (24px)

### 6.2 Icon Usage
- **Nav**: Material Symbols Outlined
- **Buttons**: Material Symbols Outlined
- **Form labels**: Material Symbols Outlined với background vàng nhạt

---

## 7. States & Interactions

### 7.1 Hover
- **Button primary**: `background-color: var(--primary-hover)`
- **Button secondary**: `background-color: rgba(255,200,74,0.15)` (vàng nhạt)
- **Nav item**: `background: rgba(0,0,0,0.04)`
- **Close button**: `hover:border-[var(--primary)]`

### 7.2 Focus
- **Input/Select**: `focus:ring-2 focus:ring-[var(--primary)]` (vàng)
- **Button**: `focus:ring-2 focus:ring-offset-2 focus:ring-[var(--primary)]`

### 7.3 Active
- **Nav item**: `background: rgba(0,0,0,0.06)` + `border-left: 3px solid var(--primary)`
- **Step indicator**: `background-color: var(--primary)`, `border-color: var(--border)`

### 7.4 Disabled
- **Text color**: `var(--text-secondary)`
- **Opacity**: `opacity-50`

---

## 8. Patterns

### 8.1 Wizard (Multi-step form)
- **Sidebar**: width `w-72`, background `var(--primary-light)`
- **Step indicator**: số tròn `w-10 h-10`, active = nền vàng, viền xám
- **Step text**: active/completed = `color: var(--text-main)` (không vàng)
- **Connector**: `var(--border)` (xám)
- **Panel**: `hidden` khi không active, hiện khi active

### 8.2 Dropdown với Search
- **Trigger**: button giống input, có icon `expand_more`
- **Panel**: `absolute`, `z-50`, `max-height: 320px`
- **Search input**: border xám, focus ring vàng
- **List items**: hover = `rgba(255,200,74,0.12)` (vàng nhạt)
- **Empty state**: "Không có kết quả."

### 8.3 Modal/Popup
- **Backdrop**: `rgba(0,0,0,0.4)` với `backdrop-blur-sm`
- **Modal**: `rounded-2xl`, `border-2`, `border-color: var(--border)`
- **Height**: `min(90vh, 720px)`
- **Close**: click backdrop, nút X, hoặc Escape

---

## 9. Checklist

Trước khi commit UI, kiểm tra:

### Màu sắc
- [ ] Button primary dùng `var(--primary)` và `var(--border-button)`
- [ ] Tất cả border khác dùng `var(--border)` (xám nhạt)
- [ ] Không có border vàng ngoài button primary
- [ ] Nền trắng (`var(--surface-solid)`), không vàng nhạt

### Typography
- [ ] Nav items: `14px`
- [ ] Nav title: `text-sm`
- [ ] Text trong input: `#000` (đen)

### Components
- [ ] Button có border 2px
- [ ] Input/Select có border 2px, focus ring vàng
- [ ] Card có border 2px, nền trắng
- [ ] Nav active có background xám nhạt + border-left vàng

### States
- [ ] Hover: button primary = vàng đậm, button secondary = vàng nhạt
- [ ] Focus: ring vàng (`var(--primary)`)
- [ ] Active: nav item có background + border-left vàng

### Layout
- [ ] Nav width `w-60` (240px)
- [ ] Content area `flex-1`
- [ ] Panel inactive có `hidden`

### Icons
- [ ] Material Symbols Outlined
- [ ] Nav icons: `18px`
- [ ] Button icons: `24px`

### Spacing
- [ ] Padding nhất quán (p-4, p-6)
- [ ] Gap giữa elements (gap-2, gap-3)
- [ ] Border radius: `rounded-xl` cho card/button, `rounded-lg` cho input

---

## 📝 Notes

- **Luôn dùng CSS variables** từ `design-system.css`, không hard-code màu.
- **Button primary** là **duy nhất** dùng màu vàng cho border và background.
- **Tất cả border khác** đều xám nhạt (`var(--border)`).
- **Nền trắng** cho tất cả (không vàng nhạt).
- **Hover/Focus** dùng vàng (`var(--primary)`) cho tương tác.

---

**File này là nguồn tham chiếu chính cho mọi UI trong project AIxPerf.**
