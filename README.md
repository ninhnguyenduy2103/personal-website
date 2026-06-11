# Website cá nhân — Ninh Nguyen

Trang web một trang (one-page), tĩnh, không dùng framework — toàn bộ nằm trong file [`index.html`](index.html).

- **Live**: https://ninhnguyenduy2103.github.io/personal-website/
- **Repo**: https://github.com/ninhnguyenduy2103/personal-website

## Nội dung trang

- Avatar (`avatar.png`) đặt cạnh tên và tagline trên desktop, xếp dọc trên mobile.
- Tên: **Ninh Nguyen**
- Tagline: *Học theo câu hỏi. Kết nối qua trải nghiệm.*
- Câu quote giới thiệu (đặt trong dấu ngoặc kép “ ”): *Mối quan tâm của tôi nằm ở giao điểm giữa giáo dục, văn hóa và mối quan hệ giữa con người với nhau, với cộng đồng và với Trái Đất.*
- 2 ô thông tin (`info-grid`):
  1. **Đôi nét về công việc** — giới thiệu công việc hiện tại và các dự án cá nhân.
  2. **Những điều tôi đang nuôi dưỡng** — danh sách 5 mục: tập thơ thiếu nhi, Quỹ Giáo Viên Hạnh Phúc, Trường Học Hạnh Phúc (Eurasia Learning Institute), Actions for Happiness, lối sống xanh.
- 2 nút CTA:
  - **Kết nối trên LinkedIn** ↗ (nền hồng phấn) → https://www.linkedin.com/in/ninhnguyen2103/
  - **Vòng tròn dưới tán cây** ↗ (nền xanh rừng đậm, nổi bật) → dự án cá nhân trên Facebook (https://www.facebook.com/ninh.peace)
- Liên hệ: email và số điện thoại nằm cùng hàng, mỗi mục có icon (thư / điện thoại).
- Nền trang trí: 4 cụm hình tròn (SVG) đặt ở 4 góc màn hình, dùng các màu trong bảng màu với độ mờ khác nhau.

## Yêu cầu thiết kế

### Bảng màu
| Vai trò | Màu | Mã |
|---|---|---|
| Màu chính (tiêu đề, heading) | Xanh rừng đậm | `--forest: #2F4538` |
| Màu phụ | Sage green | `--sage: #B7C4B0` |
| Màu phụ (nền section) | Sage nhạt | `--sage-soft: #DCE5D6` |
| Màu phụ | Hồng phấn | `--powder-pink: #F6DDE1` |
| Màu nhấn (quote, CTA, icon) | Hồng đất | `--terracotta: #C97B5F` |
| Màu neo (quote sang, heading phụ, icon, line/frame) | Nâu đậm | `--brown: #5A4434` |
| Nền chính | Trắng ngà | `--ivory: #FBF7F2` |

### Font chữ
- **Cormorant Garamond** (thay cho Bogart — font trả phí chưa có): dùng cho tiêu đề (`h1`), tagline, câu quote, heading phụ — tạo cảm giác premium / wellness.
- **Montserrat**: dùng cho body text, caption, CTA, thông tin liên hệ.

### Bố cục
- `.wrap` (max-width 920px, mở rộng 1100–1200px trên desktop lớn) chứa toàn bộ nội dung, căn giữa trang.
- `.narrow` (max-width 640px) áp dụng cho header, quote, CTA, contact để các phần này không quá rộng, trong khi `.info-grid` được phép rộng hơn.
- `.info-grid`: 1 cột trên mobile, 2 cột (Đôi nét về công việc | Những điều tôi đang nuôi dưỡng) từ `min-width: 760px`.
- Trên mobile: avatar ở trên cùng, sau đó tên/tagline/quote, rồi đến 2 ô info-grid (công việc trước, nuôi dưỡng sau), CTA, cuối cùng là liên hệ — đảm bảo cuộn xuống vẫn đủ nội dung, chữ không quá nhỏ.
- Trên desktop fullscreen (`min-width: 1024px`): thu gọn khoảng cách (avatar nhỏ lại còn 100px, giảm margin/padding các section, quote thu gọn) để toàn bộ trang vừa trong 1 viewport, không cần cuộn.
- Từ `min-width: 1280px`: câu quote hiển thị trên 1 dòng duy nhất (không bị xuống dòng).

### Hình nền trang trí
- 4 SVG đặt cố định (`position: fixed`) ở 4 góc (`.bg-deco.tl/.tr/.bl/.br`), mỗi SVG là tập hợp các hình tròn với màu trong bảng màu, độ mờ 0.18–0.5, kích thước theo đơn vị `vmin` để không bị crop khi mở fullscreen.

## Tóm tắt các thay đổi đã thực hiện

1. **Khởi tạo trang**: tạo trang một trang với tên, tagline, quote, link LinkedIn.
2. **Áp dụng bảng màu & font**: theo bảng màu xanh rừng / sage / hồng phấn / hồng đất / nâu đậm / trắng ngà, font Cormorant Garamond + Montserrat.
3. **Thêm nút CTA thứ 2** "Vòng tròn dưới tán cây" liên kết tới trang Facebook dự án cá nhân; điều chỉnh màu 2 nút (LinkedIn nhạt hơn, dự án nền xanh đậm nổi bật).
4. **Thêm avatar và thông tin liên hệ** (email, số điện thoại); chỉnh `object-position` để ảnh đại diện không bị crop mất phần đầu/trán.
5. **Sửa lỗi hiển thị ảnh** do macOS lưu tên file Unicode dạng NFD — đổi tên file ảnh thành `avatar.png` (ASCII).
6. **Chỉnh độ dài câu quote** để không bị rớt dòng quá nhiều trên màn hình hẹp.
7. **Thêm hình nền trang trí** dạng các vòng tròn ở 4 góc màn hình; sửa các lỗi:
   - Vòng tròn bị ẩn do stacking context (`position: relative` + `z-index: -1`).
   - Vòng tròn bị crop khi mở fullscreen do dùng 1 SVG `preserveAspectRatio="slice"` → tách thành 4 SVG riêng theo từng góc.
   - Dọn các vệt màu/nền thừa còn sót lại ở các góc.
8. **Thêm mục "Những điều tôi đang nuôi dưỡng"** (5 gạch đầu dòng) vào ô thứ 2 của `info-grid`, đặt cạnh "Đôi nét về công việc" để không cần cuộn thêm trên desktop.
9. **Tối ưu bố cục responsive**:
   - Mở rộng `.wrap` lên 920px (rồi 1100–1200px trên desktop lớn) để 2 cột info-grid không bị hẹp/dài quá ("ốm").
   - Thêm media query thu gọn khoảng cách dọc (avatar, margin, padding) cho desktop fullscreen để vừa 1 trang, không cần cuộn.
10. **Redesign header**: đưa avatar sang cạnh tên + tagline (xếp dọc) trên desktop; sửa lỗi gạch chân (divider) bị căn giữa/lệch do xung đột CSS.
11. **Quote**: bỏ viền cam 2 bên, tăng cỡ chữ, thêm dấu ngoặc kép “ ” màu hồng đất; trên màn hình rộng (≥1280px) hiển thị trên 1 dòng.
12. **Liên hệ & footer**: đưa email và số điện thoại về cùng 1 hàng; xoá dòng chữ "NINH NGUYEN" mờ ở footer để tiết kiệm khoảng trống.
13. **Triển khai GitHub Pages**: khởi tạo git, push code lên repo `ninhnguyenduy2103/personal-website`, bật GitHub Pages từ nhánh `main`.

## Cách chỉnh sửa / triển khai

1. Sửa trực tiếp file `index.html` (HTML, CSS đều nằm trong 1 file).
2. Mở bằng trình duyệt để xem trước (mở file `index.html` trực tiếp, hoặc dùng live preview).
3. Khi ưng ý, chạy:
   ```bash
   git add index.html
   git commit -m "Mô tả thay đổi"
   git push
   ```
4. GitHub Pages sẽ tự cập nhật sau vài phút tại link live ở trên.
