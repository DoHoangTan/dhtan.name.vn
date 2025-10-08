# dhtan.name.vn — Danh thiếp số + Cổng hỗ trợ (no-backend)

## Cấu trúc
```
/
├─ index.html          # Trang danh thiếp chính
├─ work/
│  ├─ form.html        # Cổng hỗ trợ: nhập mã + redirect
│  └─ thanks.html      # Trang cảm ơn
├─ assets/
│  ├─ styles.css
│  ├─ favicon.svg
│  └─ logo.svg
├─ robots.txt          # Chặn index thư mục /work/
├─ sitemap.xml         # Sitemap chỉ index trang chủ
└─ CNAME               # Dùng cho GitHub Pages custom domain
```

## Hướng dẫn triển khai
1. Tạo repo GitHub (ví dụ: `dhtan-name-vn`), push toàn bộ file lên branch `main`.
2. Vào Settings → Pages → Source: `Deploy from a branch`, Branch: `main` / root (`/`).
3. Chờ GitHub Pages build, bật "Enforce HTTPS".
4. Tại nhà cung cấp domain, tạo CNAME `dhtan.name.vn` → trỏ tới `{username}.github.io`.
5. Giữ file `CNAME` trong repo với nội dung `dhtan.name.vn` (đã có sẵn).

## Cấu hình điểm đến
- Mở `work/form.html`, thay:
  - `https://docs.google.com/forms/d/e/FORM_ID/viewform`
  - `https://docs.google.com/spreadsheets/d/SHEET_ID/view`
- Nếu muốn auto-fill `?agent=...` vào Google Form, tạo prefilled link hoặc dùng Apps Script trung gian (không bắt buộc).

## Bảo mật & riêng tư
- Dữ liệu chỉ đi qua hệ sinh thái Google (Forms/Sheets). Trang này không lưu dữ liệu.
- `robots.txt` đã chặn thu thập `/work/`. Nếu cần nghiêm ngặt hơn, có thể thêm meta `noindex` ở các trang phụ (đã thêm).

## Nâng cấp (tuỳ chọn)
- GA4: thêm mã đo lường vào `index.html`.
- PWA: thêm `manifest.webmanifest` + service worker nếu muốn "Add to Home Screen" như app.
- Thêm `humans.txt`/`security.txt` nếu cần.
