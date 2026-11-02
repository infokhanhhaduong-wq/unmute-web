# UNMUTE — Website (landing page)

Trang chủ UNMUTE dạng web tĩnh: một file `index.html` (HTML + CSS + JavaScript) và thư mục `assets/`. Không cần cài đặt, không cần framework, không cần server riêng.

## Cấu trúc

```
unmute-web/
├── index.html          Toàn bộ trang: giao diện, style và script (rút lá, tab bộ bài)
├── README.md
└── assets/
    ├── logo-horizontal.png        Logo ngang, nền sáng (header)
    ├── logo-horizontal-white.png  Logo ngang, bản trắng (footer, nền đen)
    ├── logo-icon.png              Biểu tượng hai lá bài (favicon, lá bài)
    ├── poster-*.webp              Poster 4 bộ bài
    └── icon-*.png                 Icon 4 bộ bài
```

## Xem thử trên máy

Mở `index.html` bằng trình duyệt (nhấp đúp). Font Bricolage Grotesque và Be Vietnam Pro tải từ Google Fonts nên cần có mạng.

## Đưa lên web

**Cách nhanh nhất (không cần GitHub):** vào Netlify Drop (app.netlify.com/drop), kéo cả thư mục `unmute-web` vào. Vài giây sau bạn có link công khai.

**Cách nên dùng lâu dài:**
1. Tạo repository trên GitHub (ví dụ `unmute-web`), tải toàn bộ thư mục này lên (giữ nguyên cấu trúc, `index.html` nằm ở gốc).
2. Vào Vercel, Netlify hoặc Cloudflare Pages → tạo project mới → chọn repository đó.
3. Không cần build command. Output directory để trống hoặc `/`. Bấm Deploy.
4. Mỗi lần sửa file trên GitHub, trang sẽ tự cập nhật.

**Gắn tên miền:** trong mục Domains của hosting, thêm tên miền (ví dụ `unmute.vn`) rồi trỏ DNS theo hướng dẫn hiện ra. HTTPS thường được cấp tự động.

## Sửa nội dung thường gặp

- **Câu hỏi trên lá bài ở hero:** tìm `var cards = [` trong phần `<script>` cuối file.
- **Thông tin 4 bộ bài:** tìm `var decks = [` (tên, tagline, đối tượng, nội dung, bối cảnh, màu).
- **Chữ còn lại:** sửa trực tiếp trong HTML.
- **Thay ảnh:** ghi đè file trong `assets/` với cùng tên.

## Việc cần làm trước khi công bố

- [ ] Thay logo bằng file gốc SVG/PNG (bản hiện tại được cắt từ PDF brand guideline).
- [ ] Điền các placeholder: giá (`[CẬP NHẬT KHI CHỐT MÔ HÌNH GIÁ]`), `[LINK ĐĂNG KÝ]`, ảnh chiến dịch và ảnh khoảnh khắc thật.
- [ ] Quyết định nút “Chơi ngay”: hiện dẫn tới phần rút thử ở hero (`#play`). Khi có game thật hoặc trang đăng ký chờ, đổi các `href="#play"`.
- [ ] Tạo trang Quyền riêng tư, Điều khoản, Liên hệ (link footer đang là `#privacy`, `#terms`, `#contact`).
- [ ] Chỉ giữ câu “Câu trả lời không được ghi lại” nếu sản phẩm thật sự không lưu.
- [ ] Xác nhận “2–8 người chơi” đúng với thiết kế game.
- [ ] Thêm ảnh chia sẻ mạng xã hội 1200×630 và khai báo `og:image`, `og:url` trong `<head>`.
- [ ] Thêm analytics cho các sự kiện chính (landing_view, deck_selected, card_revealed, card_skipped). Không gửi nội dung câu hỏi hay câu trả lời.
- [ ] Kiểm tra trên điện thoại thật: dấu tiếng Việt, tốc độ tải, hiệu ứng blur trên máy cấu hình yếu.
