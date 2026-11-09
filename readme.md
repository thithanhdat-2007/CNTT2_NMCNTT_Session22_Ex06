# BÀI TẬP 6: TỔNG HỢP KỸ NĂNG DÙNG PROMPT AI & BUG REPORTING XỬ LÝ LỖI QUYỀN TRUY CẬP HỆ THỐNG

## I. Đề bài & Yêu cầu

1. **Mục tiêu**: Tổng hợp kỹ năng dùng Prompt AI và Bug Reporting để giải quyết lỗi quyền truy cập hệ thống.
2. **Bối cảnh**: Bạn đang cần đẩy code lên GitHub để kịp deadline, nhưng Terminal báo lỗi: `error: open(".git/FETCH_HEAD"): Permission denied`. Bạn đã thử chạy lại nhưng không được.
3. **Yêu cầu chức năng**:
   - Sử dụng **Công thức Prompt 3 Thành phần** để nhờ AI giải thích lỗi này một cách bình dân nhất.
   - Giả sử AI hướng dẫn bạn dùng quyền **Run as Administrator**, hãy thực hiện và trình bày nguyên tắc chụp ảnh màn hình minh họa chuyên nghiệp (khoanh vùng lỗi, bảo mật thông tin cá nhân).
   - Nếu vẫn không sửa được, hãy soạn một tin nhắn nhờ giảng viên hỗ trợ tuân thủ đúng **Bug Reporting Framework**.
   - Đúc kết ý nghĩa thực tiễn sau toàn bộ chuỗi 6 bài tập.

## II. Bài làm chi tiết

### Câu 1: Sử dụng Công thức Prompt 3 Thành phần nhờ AI giải thích lỗi bình dân nhất

**Cấu trúc Prompt 3 Thành phần:**
1. **Thành phần 1 – Bối cảnh & Vai trò (Role & Context)**: *"Bạn là một người hướng dẫn Git cho sinh viên năm nhất. Tôi đang dùng máy tính Windows 11 và chạy lệnh đồng bộ/đẩy code lên GitHub trong Git Bash."*
2. **Thành phần 2 – Vấn đề & Dữ liệu lỗi (Problem / Input)**: *"Terminal trả về thông báo lỗi: `error: open(".git/FETCH_HEAD"): Permission denied`."*
3. **Thành phần 3 – Yêu cầu đầu ra (Output Requirement)**: *"Hãy giải thích nguyên nhân lỗi này bằng ngôn ngữ đời thường, bình dân nhất (ví dụ ẩn dụ với cuốn sổ ghi chép hoặc ổ khóa), không dùng thuật ngữ chuyên ngành phức tạp, và gợi ý cách kiểm tra nhanh."*

**Bản giải thích bình dân thu được:**
> Hãy tưởng tượng thư mục `.git` là phòng làm việc riêng của Git, còn tệp `FETCH_HEAD` là **cuốn sổ nháp** ghi lại lần gần nhất bạn kéo dữ liệu từ trên mạng về. Lỗi `Permission denied` nghĩa là Git muốn mở cuốn sổ nháp đó ra ghi chép tiếp nhưng **bị khóa trái cửa**. Có 2 lý do phổ biến nhất:
> 1. Lần trước bạn lỡ mở Git bằng quyền "Sếp tổng" (**Run as Administrator**), nên cuốn sổ bị đóng dấu chỉ "Sếp tổng" mới được sửa; lần này bạn mở Git bằng tài khoản thường nên bị từ chối.
> 2. Có một chương trình khác trên máy (như VS Code hoặc phần mềm diệt virus) đang mở và giữ chặt cuốn sổ đó chưa chịu buông ra.

### Câu 2: Nguyên tắc chụp ảnh màn hình minh họa chuyên nghiệp khi thử "Run as Administrator"

Khi chụp ảnh màn hình cửa sổ Terminal chạy quyền `Administrator: Git Bash` để làm bằng chứng báo lỗi, cần tuân thủ 3 tiêu chuẩn kỹ thuật:
* **Hiển thị rõ trạng thái thực thi**: Chụp kèm thanh tiêu đề cửa sổ có dòng chữ `Administrator: Git Bash` (hoặc `Administrator: Windows PowerShell`) và câu lệnh vừa gõ (`git pull origin main`).
* **Khoanh vùng lỗi trọng tâm (Annotation)**: Dùng khung chữ nhật màu đỏ tươi khoanh trực tiếp vào dòng chữ `error: open(".git/FETCH_HEAD"): Permission denied` để người xem nhận diện lỗi trong 1 giây.
* **Bảo mật thông tin cá nhân (Redaction)**: Che mờ hoặc phủ kín các thông tin nhạy cảm trên Terminal như tên người dùng máy tính (`C:\Users\<Tên_Cá_Nhân>`), địa chỉ IP nội bộ hoặc mã Token cá nhân (`[REDACTED_USER]`).

### Câu 3: Tin nhắn nhờ giảng viên hỗ trợ tuân thủ chuẩn Bug Reporting Framework (4 Mảnh Ghép)

```text
Em chào thầy/cô ạ, em đang gặp lỗi quyền truy cập tệp .git/FETCH_HEAD khi đồng bộ code lên GitHub để nộp bài. Em đã thử tự tra cứu và chạy lại bằng quyền Administrator nhưng vẫn chưa khắc phục được, nhờ thầy/cô xem và hỗ trợ giúp em với ạ:

1. Context (Bối cảnh & Môi trường):
- Hệ điều hành: Windows 11 64-bit, sử dụng Git Bash (phiên bản 2.44.0).
- Thao tác thực hiện: Chạy lệnh `git pull origin main` tại thư mục dự án trước khi đẩy (push) bài tập lên GitHub.

2. Expected (Kết quả kỳ vọng):
- Git mở và cập nhật được tệp `.git/FETCH_HEAD`, đồng bộ nhánh `main` thành công để cho phép đẩy code mới lên kho lưu trữ.

3. Actual (Kết quả thực tế):
- Lệnh bị dừng ngay lập tức và báo lỗi từ chối quyền mở tệp `.git/FETCH_HEAD`.

4. Log & Các bước đã tự xử lý (Trace & Troubleshooting):
- Log lỗi văn bản:
  $ git pull origin main
  error: open(".git/FETCH_HEAD"): Permission denied
  fatal: Cannot open .git/FETCH_HEAD
- Các cách em đã thử:
  (1) Đã đóng toàn bộ cửa sổ VS Code và mở lại Git Bash bằng quyền "Run as Administrator" (như ảnh chụp màn hình em đính kèm bên dưới).
  (2) Đã kiểm tra phần Properties của thư mục `.git` để bỏ chọn Read-only nhưng tệp FETCH_HEAD vẫn báo khóa quyền truy cập.

Em cảm ơn thầy/cô ạ!
```

### Câu 4: Tổng kết & Đúc kết ý nghĩa sau chuỗi 6 bài tập thực hành

Sau toàn bộ chuỗi bài tập, giá trị cốt lõi đúc kết được là **hệ tư duy làm việc độc lập, an toàn và chuyên nghiệp của người làm Công nghệ Thông tin**:

1. **Tìm kiếm thông minh thay vì "mò kim đáy bể"**: Làm chủ các toán tử tìm kiếm nâng cao (`" "`, `filetype:pdf`, `site:`, `-site:`) giúp đi thẳng vào kho học liệu chính thống của nhà trường (`ptit.edu.vn`) hoặc tài liệu gốc của nhà sản xuất, tiết kiệm thời gian và miễn nhiễm với bẫy nạp thẻ hay mã độc.
2. **Đánh giá thông tin có tư duy phản biện, không tin mù quáng vào "Tích xanh"**: Hiểu được sự đánh đổi (Trade-off) trên StackOverflow — một câu trả lời mới phù hợp với hệ điều hành hiện tại (Windows 11) có giá trị hơn một dấu tích xanh (`✓`) đã lỗi thời từ 10 năm trước; đồng thời biết tận dụng chỉ số `👍`, `❤️` và nhãn `Maintainer` trên GitHub Issues để tìm **Workaround** kịp chạy tiến độ dự án.
3. **Làm chủ AI an toàn (Chống AI Hallucination)**: Biết dùng **Công thức Prompt 3 thành phần** để biến AI thành người giải thích lỗi dễ hiểu, nhưng luôn áp dụng **mô hình IPO** (kiểm chứng chéo trên trang chủ và hỏi ngược lại AI về rủi ro/cách hoàn tác) trước khi chạy lệnh lạ trên Terminal.
4. **Tự cứu mình trước khi hỏi và giao tiếp kỹ thuật văn minh**: Áp dụng **Quy trình 3 bước (Googling ➔ Community ➔ AI)** giúp tự xử lý 80% sự cố môi trường. Khi cần sự trợ giúp từ giảng viên hoặc đồng nghiệp, việc cung cấp đủ **4 mảnh ghép (Context – Expected – Actual – Log)** kèm ảnh chụp màn hình chuẩn chỉnh giúp người hỗ trợ bắt đúng bệnh ngay lập tức, nâng cao hiệu suất làm việc của cả tập thể.
