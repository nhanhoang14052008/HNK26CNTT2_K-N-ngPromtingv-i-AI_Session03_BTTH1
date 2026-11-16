# PROMPT CREATE – TRÍCH XUẤT THÔNG TIN TUYỂN DỤNG

**C – Context:** Bạn là chuyên viên xử lý dữ liệu nhân sự cấp cao tại công ty công nghệ.

**R – Request:** Trích xuất 6 thông tin từ email ứng tuyển: Họ tên, Số điện thoại, Email, Vị trí ứng tuyển, Năm kinh nghiệm, Kỹ năng chính.

**E – Explanation:** Dữ liệu dùng để nhập vào database tuyển dụng, yêu cầu chính xác, không suy đoán hoặc bịa đặt.

**A – Action:** Đọc email, trích xuất và chuẩn hóa thông tin; viết hoa chữ cái đầu họ tên, chuẩn hóa số điện thoại theo mã +84, gom kỹ năng thành danh sách không trùng lặp. Thiếu thông tin ghi `null`, kỹ năng thiếu ghi `[]`.

**T – Tone:** Chính xác, khách quan, chuyên nghiệp, ngắn gọn.

**E – Extras (Few-shot):**

**Ví dụ 1:**
- Input: "Tôi là NGUYỄN HOÀNG TRÍ NHÂN, ứng tuyển Backend Developer, có 2 năm kinh nghiệm Python, SQL. SĐT 0912345678, email nhan@gmail.com."
- Output: `{"name":"Nguyễn Hoàng Trí Nhân","phone":"+84919982386","email":"nhan@gmail.com","position":"Backend Developer","experience_years":2,"skills":["Python","SQL"]}`

**Ví dụ 2:**
- Input: "Tôi là Trần Hoàng Long, ứng tuyển Frontend Developer, có 1 năm kinh nghiệm HTML, CSS. Email long@gmail.com."
- Output: `{"name":"Trần Hoàng Long","phone":null,"email":"long@gmail.com","position":"Frontend Developer","experience_years":1,"skills":["HTML","CSS"]}`

**Email đầu vào:** `{{email_raw}}`

**Yêu cầu đầu ra:**

1. Bảng Markdown:

| Họ tên | Số điện thoại | Email | Vị trí | Kinh nghiệm | Kỹ năng |
|---|---|---|---|---|---|
| ... | ... | ... | ... | ... | ... |

2. Mảng Raw JSON:

```json
[
  {
    "name": "...",
    "phone": null,
    "email": "...",
    "position": "...",
    "experience_years": null,
    "skills": []
  }
]
```

**Ràng buộc:** Chỉ trả về bảng Markdown và JSON hợp lệ; không thêm giải thích, không tự tạo thông tin. Kiểm tra JSON bằng công cụ Validate JSON trước khi xuất.
