# thong-tin-so-ET3250

Tài liệu Thông tin số ET3250 của Nguyễn Đức Luân, soạn bằng LaTeX.

## Đọc tài liệu

Trang đọc tài liệu sau khi triển khai thành công tại
[ndluank69.github.io/thong-tin-so-ET3250](https://ndluank69.github.io/thong-tin-so-ET3250/).
Trang có bản PDF nhúng, nút mở PDF và nút tải về.

## Bật GitHub Pages

1. Đẩy các tệp `index.html` và `.github/workflows/deploy.yml` lên nhánh `main`.
2. Mở **Settings → Pages → Build and deployment → Source**, chọn **GitHub Actions**.
3. Vào **Actions → Deploy GitHub Pages → Run workflow**, chọn nhánh `main` và chạy.
4. Chờ hai job `build` và `deploy` hoàn tất, rồi mở đường dẫn trang ở trên.

Mỗi lần đẩy thay đổi lên `main`, workflow sẽ biên dịch `main.tex` bằng XeLaTeX,
đóng gói trang HTML cùng bản PDF vừa tạo và triển khai lên GitHub Pages.

Workflow nằm tại `.github/workflows/deploy.yml` để GitHub Actions nhận diện.
Cấu hình theo
[hướng dẫn GitHub Pages](https://docs.github.com/en/pages/getting-started-with-github-pages/using-custom-workflows-with-github-pages).

## Xem trên máy

Cài XeLaTeX, `latexmk` và phông DejaVu Serif, sau đó chạy từ thư mục dự án.

```sh
latexmk -xelatex -interaction=nonstopmode -halt-on-error main.tex
python3 -m http.server 8000
```

Mở [localhost:8000](http://localhost:8000/) để đọc tài liệu qua `index.html`.
