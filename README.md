# Hướng Dẫn Soạn Thảo Dự Án LaTeX Nhóm (10 Bài)

Chào mừng bạn đến với dự án LaTeX của nhóm! Tài liệu này hướng dẫn cách thiết lập môi trường và quy trình làm việc chung cho dự án gồm **10 bài viết/chương**.

---

## 📁 Cấu Trúc Thư Mục Dự Án

Để 10 người (hoặc nhiều người) có thể viết 10 bài cùng lúc mà không bị xung đột file, dự án được tổ chức theo cấu trúc sau:

```text
├── main.tex               # File chính (chỉ chứa cấu hình và gọi các bài)
├── main.pdf               # File kết quả xuất ra (không push lên Git)
├── references.bib         # Thư mục chứa tài liệu tham khảo chung
├── .gitignore             # File cấu hình bỏ qua các file rác khi biên dịch
└── chapters/              # Thư mục chứa nội dung của 10 bài
    ├── bai_01.tex         # Nội dung Bài 1
    ├── bai_02.tex         # Nội dung Bài 2
    ├── bai_03.tex         # Nội dung Bài 3
    ├── bai_04.tex         # Nội dung Bài 4
    ├── bai_05.tex         # Nội dung Bài 5
    ├── bai_06.tex         # Nội dung Bài 6
    ├── bai_07.tex         # Nội dung Bài 7
    ├── bai_08.tex         # Nội dung Bài 8
    ├── bai_09.tex         # Nội dung Bài 9
    └── bai_10.tex         # Nội dung Bài 10
```

* **Quy tắc:** Mỗi thành viên được phân công bài nào thì **chỉ chỉnh sửa đúng file `.tex` của bài đó** trong thư mục `chapters/`. Hạn chế tối đa việc sửa file `main.tex`.

---

## 🛠️ Cài Đặt Môi Trường (Cho Người Mới)

### 1. Cài đặt Trình biên dịch (TeX Distribution)
Tùy thuộc vào hệ điều hành của bạn, hãy tải và cài đặt phiên bản phù hợp:
* **Windows:** Tải và cài đặt [MiKTeX](https://miktex.org) hoặc [TeX Live](https://tug.org).
* **macOS:** Tải và cài đặt [MacTeX](https://tug.org).
* **Linux:** Chạy lệnh `sudo apt install texlive-full`.

### 2. Cài đặt Trình soạn thảo (Editor)
Khuyến khích cả nhóm sử dụng **Visual Studio Code (VS Code)**:
1. Tải và cài đặt [VS Code](https://visualstudio.com).
2. Vào mục **Extensions** (Ctrl+Shift+X), tìm và cài đặt **LaTeX Workshop**.
3. Cài đặt thêm extension **GitLens** để dễ theo dõi ai đã sửa những gì.

---

## 🚀 Quy Trình Cập Nhật Bài Viết (Git Workflow)

Trước khi viết hoặc sau khi viết xong một phần, hãy tuân thủ các bước:

* **Bước 1 (Trước khi viết):** Chạy lệnh `git pull` để cập nhật bài của các thành viên khác về máy mình.
* **Bước 2 (Viết bài):** Chỉ chỉnh sửa file được phân công (Ví dụ: `chapters/bai_01.tex`). Nhấn `Ctrl + S` để biên dịch thử xem có lỗi cú pháp không.
* **Bước 3 (Lưu và gửi bài):** Khi đã hoàn thành, chạy các lệnh sau tại terminal để đẩy bài lên:
  ```bash
  git add chapters/bai_XX.tex  # Thay XX bằng số bài của bạn để an toàn
  git commit -m "Hoàn thành nội dung Bài XX - [Tên của bạn]"
  git push origin main
  ```

---

## ⚠️ Lưu Ý Quan Trọng khi dùng LaTeX

* **Không push file rác:** Khi biên dịch LaTeX sẽ sinh ra rất nhiều file phụ trợ (`.aux`, `.log`, `.toc`). Vui lòng không dùng lệnh `git add .` một cách bừa bãi để tránh đẩy file rác lên kho chung.
* **Định dạng tiếng Việt:** Đảm bảo trình soạn thảo của bạn đang bật mã hóa **UTF-8** để không bị lỗi font.
* **Lỗi biên dịch:** Nếu gặp lỗi không thể xuất PDF, hãy kiểm tra lại cửa sổ log ở góc dưới màn hình xem dòng lệnh nào bị viết sai cú pháp (thiếu dấu `}`, dấu `$` hoặc chưa đóng môi trường `\end{}`).
