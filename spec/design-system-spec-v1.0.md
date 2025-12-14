# Design System Spec v1.0

> **Status:** Locked Core (Additive updates only)
>
> **Purpose:** Đây là đặc tả chính thức cho hệ Design System dùng cho **AI tự sinh UI**. Tài liệu này đóng vai trò *nguồn hiểu biết* (semantic source of truth) cho cả con người và AI.

---

## 1. Triết lý thiết kế (Design Philosophy)

### 1.1 AI-first, không phải human-first
- Hệ thống này được thiết kế để **AI hiểu – tuân – sinh UI ổn định** qua thời gian.
- Ưu tiên **tính nhất quán, khả năng kiểm soát và khả năng mở rộng có luật** hơn sự sáng tạo tự do.

### 1.2 Token-driven, không implementation-driven
- Mọi quyết định về màu sắc, kích thước, shadow, motion **phải truy vết được về token**.
- CSS, HTML, JS chỉ là implementation – **không phải nguồn chân lý**.

### 1.3 Visual Language: Physical & Industrial
- Ngôn ngữ thị giác chính:
  - **3D Press / Physical Depth** (shadow có hướng, có trạng thái)
  - **Glass / Frosted Surface** cho panel lớn
  - **Motion ngắn, dứt khoát, có chủ đích**

---

## 2. Token Architecture

### 2.1 Phân cấp Token

1. **Foundation Tokens**
   - Color (brand, neutral, surface)
   - Radius
   - Motion (duration, easing)
   - Shadow depth

2. **Component Tokens**
   - Button
   - Knob
   - Sidebar
   - Tag

> ⚠️ Component token **không được override foundation token trực tiếp** nếu không có lý do thiết kế rõ ràng.

---

## 3. Core Components (Locked)

Các component sau được xem là **core** trong v1.0. AI **không được thay đổi hành vi mặc định** của chúng.

### 3.1 Button

#### Variants (v1.0)
- Button Blue (Primary Action)
- Button Green (Feature / Success Action)

#### Shared Behavior
- Có **3D press effect**
- Trạng thái:
  - Default: nổi
  - Active / Press: chìm (shadow giảm + translateY)

#### Rules
- Không được tạo button mới nếu chưa khai báo variant
- Không dùng Button Green để thay thế Button Blue

---

### 3.2 Knob

#### Purpose
- Thành phần tương tác mô phỏng **nút vật lý**

#### Interaction Model
1. **Click nhanh (< threshold)**
   - Chỉ kích hoạt rotation icon
   - Không kích hoạt press depth

2. **Press & Hold (>= threshold)**
   - Kích hoạt trạng thái press (chìm)
   - Không xoay icon

#### Rules
- Không dùng Knob cho form input
- Không gắn animation phụ ngoài rotation được định nghĩa

---

### 3.3 Sidebar

#### Surface
- Glass / Frosted Glass

#### Layout Modes
- Desktop:
  - Floating panel
  - Push content (không overlay)
- Mobile:
  - Overlay / Fixed
  - Có backdrop

#### Rules
- Sidebar **không được che nội dung chính trên desktop**
- Glass effect chỉ dùng cho container lớn

---

### 3.4 Tag

#### States
- Inactive (default)
- Active

#### Behavior
- Hover chỉ áp dụng khi inactive
- Active thể hiện trạng thái filter / selection đang được áp dụng

#### Rules
- Không dùng Tag như Button chính
- Không gắn animation dài hoặc liên tục

---

## 4. Motion & Interaction Rules

### 4.1 Motion Principles
- Thời gian ngắn (fast feedback)
- Easing đơn giản
- Không dùng motion trang trí nếu không phục vụ trạng thái

### 4.2 Accessibility
- Mọi animation phải tôn trọng `prefers-reduced-motion`

---

## 5. Extension Policy (Rất quan trọng)

### 5.1 Allowed Extensions
- Thêm **variant mới** cho component hiện có (ví dụ: Button Yellow)
- Thêm **effect mới** có scope rõ ràng (ví dụ: RGB Glow)

### 5.2 Forbidden Changes (Breaking)
- Thay đổi hành vi mặc định của core component
- Đổi ý nghĩa semantic của component
- Sửa token cũ trong cùng major version

---

## 6. Versioning

- v1.x: Additive only
- v2.0: Breaking changes (phải tạo Spec mới)

Mọi AI khi sinh UI **phải biết rõ version đang áp dụng**.

---

## 7. Relationship to AI-ready Contract

- Spec này **mô tả ý nghĩa & luật sử dụng**
- AI-ready Contract sẽ:
  - Tham chiếu Spec này
  - Cưỡng chế các luật ở mức máy

> Spec = Hiểu
> Contract = Tuân

---

**End of Design System Spec v1.0**

