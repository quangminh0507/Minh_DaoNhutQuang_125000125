# NHẬT KÝ PROMPT ENGINEERING (VIBE CODING LOG)

**Họ và tên:** Đào Nhựt Quang Minh  
**MSSV:** 125000125  
**Tên đề tài Website:** TechWorld - Cửa Hàng Đồ Điện Tử & Công Nghệ  
**Công cụ AI đã sử dụng:** ChatGPT, Claude, Google Antigravity, Gemini  

---

## 1. Yêu cầu ban đầu (System/Initial Prompt)
> *Ghi lại prompt tổng quan ban đầu dùng để khởi tạo khung website:*
> 
> "Hãy thiết kế cho tôi mã nguồn hoàn chỉnh gồm `index.html` và `style.css` cho một website thương mại điện tử công nghệ mang tên **TechWorld**. 
> Yêu cầu kỹ thuật bắt buộc:
> 1. **Chuẩn Semantic HTML5:** Sử dụng đúng ngữ nghĩa các thẻ `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, và `<footer>`, tránh lạm dụng thẻ `<div>` vô nghĩa.
> 2. **Kỹ thuật CSS & CSS Variables:** Khai báo đầy đủ hệ thống biến `:root` quản lý màu sắc (chủ đạo công nghệ, nền tối/sáng), font chữ, khoảng cách và hiệu ứng bóng đổ.
> 3. **Layout hiện đại & Responsive:** Sử dụng kết hợp linh hoạt **CSS Flexbox** (cho Header, Navbar, thanh lọc) và **CSS Grid** (cho danh sách sản phẩm và dịch vụ) để tự động co giãn tối ưu trên mọi thiết bị.
> 4. **Hiệu ứng & Tương tác:** Tích hợp Animate.css cho tiêu đề/hero, hiệu ứng cuộn trang mượt mà, cùng các hiệu ứng `:hover`, `:focus` tự viết bằng CSS cho nút bấm và thẻ sản phẩm."

---

## 2. Quá trình tinh chỉnh & Giải quyết sự cố (Iterations)

### Lần 1: Dựng khung Semantic HTML5 & Cấu hình CSS Variables
- **Công cụ AI sử dụng:** ChatGPT & Claude  
- **Prompt đã dùng:**  
  > "Hãy tạo cấu trúc Semantic HTML5 chuẩn cho trang TechWorld gồm thanh điều hướng dính (`sticky header`), phần Hero chào mừng, danh sách sản phẩm bán chạy dạng lưới (Grid), và chân trang thông tin sinh viên Đào Nhựt Quang Minh (MSSV: 125000125). Đồng thời viết file `style.css` sử dụng khối `:root` cho biến màu sắc và Flexbox/Grid căn chỉnh layout."
- **Kết quả AI tạo ra:**  
  - Claude và ChatGPT sinh ra khung HTML cơ bản với đầy đủ `<header>`, `<nav>`, `<main>`, `<footer>` và bảng biến `:root` trong CSS quản lý màu sắc, spacing rất nhất quán.
- **Nhận xét & Tinh chỉnh của SV:**  
  - *Sự cố/Nhược điểm:* AI lạm dụng nhiều thẻ `<div>` không cần thiết bọc quanh các sản phẩm và dịch vụ. 
  - *Tinh chỉnh:* Tôi đã yêu cầu AI tái cấu trúc lại, thay thế các thẻ division thừa bằng thẻ ngữ nghĩa `<article class="product-card">` cho từng sản phẩm và `<article class="service-card">` cho từng dịch vụ để đáp ứng đúng 100% chuẩn Semantic HTML5 theo yêu cầu đề thi.

### Lần 2: Mở rộng danh mục, thiết kế UI/UX nâng cao & Tương tác thuần CSS
- **Công cụ AI sử dụng:** Google Antigravity & Gemini  
- **Prompt đã dùng:**  
  > "Hãy nâng cấp toàn bộ giao diện TechWorld trên Antigravity để bắt mắt và đa dạng hơn:  
  > 1. Bổ sung màn hình chờ Loader thuần CSS (`.page-loader`).  
  > 2. Bổ sung thanh danh mục nhanh (`.category-bar`) và hệ thống lọc danh mục/tab sản phẩm (Tất cả, 🔥 Bán chạy, ✨ Mới ra mắt, 💥 Khuyến mãi hot) bằng CSS thuần (dùng `:checked` và `:target`).  
  > 3. Bổ sung đồng hồ đếm ngược Flash Sale bằng CSS Animation `@property`.  
  > 4. Bổ sung Banner chương trình 'Thu cũ đổi mới' (`.promo-banner`) và các huy hiệu giảm giá (Badges), đánh giá sao (Star ratings)."
- **Thách thức gặp phải (Technical Issues):**  
  - *Lỗi 1 (Xung đột CSS Transform):* Khi áp dụng bộ lọc CSS thuần, thuộc tính `display: none` và `transform` khi hover (`:hover`) bị xung đột với hiệu ứng cuộn trang, làm mất độ nảy (scale) và bóng đổ của thẻ sản phẩm.  
  - *Lỗi 2 (Tương thích trình duyệt):* Thuộc tính `@property` của đếm ngược Flash Sale và `animation-timeline: view()` không hiển thị số trên một số trình duyệt chưa hỗ trợ.
- **Cách sửa prompt (Debug prompt):**  
  > "Hãy tối ưu lại file `style.css`:  
  > 1. Tách riêng thuộc tính `translate` và `scale` ra khỏi `transform` để các hiệu ứng `:hover` không đè lên hiệu ứng xuất hiện khi cuộn.  
  > 2. Bổ sung các thẻ `<span class="cd-fallback">` chứa số mặc định cho đếm ngược Flash Sale và bọc hiệu ứng cuộn trong `@supports (animation-timeline: view())` để làm fallback an toàn 100% nếu trình duyệt cũ."

---

## 3. Đánh giá cá nhân về quá trình Vibe Coding

- **AI đã giúp tiết kiệm thời gian ở phần nào nhất?**
  - **ChatGPT & Claude:** Tiết kiệm 80% thời gian dựng cấu trúc khung HTML ban đầu và thiết lập hệ thống biến màu sắc `:root` cùng các truy vấn `@media` responsive.
  - **Google Antigravity & Gemini:** Giúp tự động hóa việc viết các CSS Selector phức tạp (`:has()`, `:checked`, `:target`), tạo màn hình Loader và hiệu ứng cuộn mượt mà mà không cần phải viết thêm dòng code JavaScript nào.

- **Bài học rút ra khi đặt câu hỏi (Prompt) cho AI trong thiết kế web:**
  - **Đặt ràng buộc chặt chẽ ngay từ đầu:** Cần quy định rõ cấu trúc Semantic, các biến `:root` bắt buộc và yêu cầu không dùng JavaScript ngay trong Prompt khởi tạo để tránh việc AI sinh code thừa.
  - **Tư duy kiểm soát & tinh chỉnh (Iteration):** AI hỗ trợ tạo mã nhanh, nhưng lập trình viên phải hiểu rõ bản chất CSS (như thứ tự ưu tiên selector, cơ chế đè thuộc tính `transform`) để phát hiện lỗi giao diện và đưa ra Debug Prompt chuẩn xác.
