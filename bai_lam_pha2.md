# BÀI LÀM PHA 2 – HACKATHON 02

- **Mã đề:** 09
- **Họ tên:**Nguyễn Đăng Hoàng
- **Lớp:**CNTT1
- **Link repository Pha2:**https://github.com/hoangmit1904/HN-KS26-CNTT1_PromptAI_H02_Pha1_Pha2
- **Công cụ AI đã dùng (ChatGPT/Claude/Gemini):**Gemini

> Pha 2 (20 phút cuối). Mỗi mục: mở cuộc trò chuyện mới, gửi nguyên văn prompt đã viết trong bai_lam_pha1.md, dán câu trả lời và link chia sẻ vào đây. Xong, kéo thả file này vào repository Pha2.

## 4.2. Trích xuất tin nhắn đặt chỗ workshop ra JSON

**KET QUA AI**

```text
[
  {
    "ma_lop": "NANTAY",
    "ngay_hoc": "2026-12-13",
    "nguoi_lon": 2,
    "tre_em": 1,
    "ca_hoc": "chieu",
    "ghi_chu": null
  },
  {
    "ma_lop": "BANXOAY",
    "ngay_hoc": "2027-01-10",
    "nguoi_lon": 3,
    "tre_em": 0,
    "ca_hoc": null,
    "ghi_chu": "Một người bị đau cổ tay"
  },
  {
    "ma_lop": "VEGOM",
    "ngay_hoc": null,
    "nguoi_lon": 4,
    "tre_em": 0,
    "ca_hoc": "thuong",
    "ghi_chu": "một bạn đi xe lăn"
  }
]
```

**Link trò chuyện:**https://share.gemini.google/OThfKQEi0iCr

## 4.3. Báo giá bằng Chain-of-Thought

**KET QUA AI**

```text
Tiền người lớn:
Phép tính: $5 \times 550.000 = 2.750.000$ đồng.Tiền trẻ em:Trẻ 8 tuổi và 12 tuổi (từ 6 đến 12 tuổi): mỗi bé tính $70\%$ giá người lớn là $550.000 \times 70\% = 385.000$ đồng.Bé 4 tuổi (dưới 6 tuổi, đi kèm không làm sản phẩm): miễn phí ($0$ đồng).Phép tính: $2 \times 385.000 + 1 \times 0 = 770.000$ đồng.Tiền học (tiền người lớn + tiền trẻ em):
Phép tính: $2.750.000 + 770.000 = 3.520.000$ đồng.Giảm giá nhóm:Nhóm có $5$ người lớn (đạt điều kiện từ $5$ người lớn trở lên) nên được giảm $5\%$ trên tiền học.Phép tính: $3.520.000 \times 5\% = 176.000$ đồng (tiền học sau giảm là $3.520.000 - 176.000 = 3.344.000$ đồng).Phí nung và giao:
Phép tính: $4 \times 80.000 = 320.000$ đồng (không áp dụng giảm giá).Tổng tiền:
Phép tính: $3.344.000 + 320.000 = 3.664.000$ đồng.[RESULT: 3.664.000 đồng]
```

**Link trò chuyện:**https://share.gemini.google/y1TD2k5pScvf

### b) Kiểm tra kết quả AI



## 4.4. Dây chuyền xử lý khiếu nại – kết quả Trạm 1

**KET QUA AI**

```text
Trạm 1: Trích xuất dữ liệu (Output thực tế)
Khi đưa Prompt Trạm 1 vào mô hình AI, đầu ra trả về đúng chuẩn JSON 4 trường:

JSON
{
  "loai_su_co": "hong_san_pham",
  "so_khach": 3,
  "so_san_pham_bi_hong": 5,
  "tom_tat": "Khách nhận hàng có 5 trên 6 sản phẩm gốm bị nứt vỡ sau khi nung và giao."
}
Kiểm tra chất lượng Trạm 1: Cú pháp JSON hợp lệ, bỏ qua được thông tin nhiễu về cô hướng dẫn, đếm đúng 15 từ cho phần tóm tắt (dưới ngưỡng 20 từ).

Trạm 2: Đối chiếu chính sách & Tính mức đền bù (Giả lập trung gian)
(Trong một dây chuyền hoàn chỉnh, bước này thường dùng code hoặc một prompt nhỏ để tra bảng quy định của xưởng trước khi đẩy sang Trạm 3):

JSON
{
  "loai_su_co": "hong_san_pham",
  "so_khach": 3,
  "so_san_pham_bi_hong": 5,
  "muc_den_bu": "Hoàn 100% phí nung và giao hàng cho 5 sản phẩm hỏng, đồng thời tặng miễn phí 1 buổi học làm gốm mới cho 3 khách để làm lại sản phẩm."
}
Trạm 3: Soạn email phản hồi khách hàng (Output thực tế)
Đưa kết quả JSON từ Trạm 2 vào câu lệnh Trạm 3 của bạn, AI tạo ra email hoàn chỉnh:

Chủ đề: Phản hồi về sự cố sản phẩm gốm ngày 01/11/2026 – Đất Việt Workshop

Chào anh/chị,

Đất Việt Workshop chân thành xin lỗi anh/chị và gia đình về sự cố đáng tiếc khiến 5 sản phẩm gốm bị nứt vỡ khi nhận hàng. Chúng tôi rất tiếc vì trải nghiệm chưa trọn vẹn này.

Để khắc phục sự cố, xưởng xin gửi phương án đền bù cụ thể như sau: hoàn 100% phí nung và giao hàng cho 5 sản phẩm hỏng, đồng thời tặng miễn phí 1 buổi học làm gốm mới cho 3 khách để làm lại sản phẩm.

Anh/chị vui lòng phản hồi lại email này kèm thông tin tài khoản nhận hoàn phí và khung giờ thuận tiện để xưởng sắp xếp lịch học bù cho gia đình mình nhé.

Một lần nữa xin lỗi anh/chị và mong sớm được đón tiếp gia đình tại xưởng.

Trân trọng,

Bộ phận Chăm sóc Khách hàng – Đất Việt Workshop
```

**Link trò chuyện:**https://share.gemini.google/3jCsivDyBHjs

## 4.5. Prompt chấm bài theo Rubric

**KET QUA AI**

```text
(Dán câu trả lời của AI vào đây (bấm nút Copy dưới câu trả lời) – xoá dòng này)
```

**Link trò chuyện:**
