# BÀI LÀM PHA 2 (ĐỀ LUYỆN TẬP CHỦ ĐỀ CHẠY AFFILIATE)

- **Họ tên:** Ngô Gia Hưng
- **Lớp:** CNTT 3
- **Link repository Pha2:**https://github.com/ngogiahung123/acquyff
- **Công cụ AI đã dùng (ChatGPT/Claude/Gemini):** Gemini

> Pha 2 (20 phút cuối). Mỗi mục: mở cuộc trò chuyện mới, gửi nguyên văn prompt đã viết trong bai_lam_pha1.md, dán câu trả lời và link chia sẻ vào đây. Xong, kéo thả file này vào repository Pha2.

## 4.2. Trích xuất tin nhắn đăng ký gói Affiliate ra JSON

**KET QUA AI**

```text
```json
[
  {
    "ma_goi": "TT",
    "ngay_bat_dau": "2026-12-20",
    "creator_chinh": 2,
    "thuc_tap_sinh": 1,
    "hang_tai_khoan": "thuong",
    "ghi_chu": null
  },
  {
    "ma_goi": "SP",
    "ngay_bat_dau": "2027-01-08",
    "creator_chinh": 3,
    "thuc_tap_sinh": 0,
    "hang_tai_khoan": null,
    "ghi_chu": "ngồi bàn gần cửa ra vào do đang bó bột chân"
  },
  {
    "ma_goi": "PRO",
    "ngay_bat_dau": null,
    "creator_chinh": 4,
    "thuc_tap_sinh": 0,
    "hang_tai_khoan": "vip",
    "ghi_chu": "mượn thêm đèn trợ sáng và phông xanh để quay mẫu"
  }
]

```
```

**Link trò chuyện:** https://share.gemini.google/2zIHkbtAFAaW

## 4.3. Báo giá gói Affiliate bằng Chain-of-Thought

**KET QUA AI**

```text
```python
gia_tt = 1_500_000
so_creator_chinh = 4
so_tts = 2 # 16 tuoi va 17 tuoi (deu tu 15 den duoi 18 tuoi -> tinh 60% gia Creator chinh)
gia_tts = gia_tt * 0.6
# be 7 tuoi -> duoi 15 tuoi, ngoi khu cho -> mien phi (0 dong)

tien_creator_chinh = so_creator_chinh * gia_tt
tien_tts = so_tts * gia_tts
tong_tien_goi = tien_creator_chinh + tien_tts

# Team tu 4 Creator chinh tro len -> giam 10% tren tong tien goi
giam_gia_team = tong_tien_goi * 0.10
tien_goi_sau_giam = tong_tien_goi - giam_gia_team

# Phu thu thue 2 bo mic thu am khong day: 250.000 dong/bo, khong giam gia
so_mic = 2
gia_mic = 250_000
phu_thu_thue_mic = so_mic * gia_mic

tong_tien = tien_goi_sau_giam + phu_thu_thue_mic

print(f"tien_creator_chinh: {tien_creator_chinh:,.0f}")
print(f"tien_tts: {tien_tts:,.0f}")
print(f"tong_tien_goi: {tong_tien_goi:,.0f}")
print(f"giam_gia_team: {giam_gia_team:,.0f}")
print(f"phu_thu_thue_mic: {phu_thu_thue_mic:,.0f}")
print(f"tong_tien: {tong_tien:,.0f}")


```

```text
tien_creator_chinh: 6,000,000
tien_tts: 1,800,000
tong_tien_goi: 7,800,000
giam_gia_team: 780,000
phu_thu_thue_mic: 500,000
tong_tien: 7,520,000


```

Dưới đây là chi tiết tính toán báo giá cho team KOC theo bảng giá và quy tắc đã cho:

* **Tiền Creator chính:** `4 × 1.500.000 = 6.000.000 đồng`
* **Tiền thực tập sinh:** Hai thực tập sinh (16 tuổi và 17 tuổi, đều từ 15 đến dưới 18 tuổi) tính 60% giá Creator chính (`0,6 × 1.500.000 = 900.000 đồng/người`); bé 7 tuổi (dưới 15 tuổi, ngồi khu chờ) được miễn phí (`0 đồng`). Phép tính: `2 × (0,6 × 1.500.000) + 1 × 0 = 1.800.000 đồng`
* **Tổng tiền gói:** `6.000.000 + 1.800.000 = 7.800.000 đồng`
* **Giảm giá team:** Team có 4 Creator chính (từ 4 trở lên) nên được giảm 10% trên tổng tiền gói: `0,10 × 7.800.000 = 780.000 đồng` (tiền gói sau giảm là `7.800.000 - 780.000 = 7.020.000 đồng`)
* **Phụ thu thuê mic:** `2 × 250.000 = 500.000 đồng` (không áp dụng giảm giá)
* **Tổng tiền:** `(7.800.000 - 780.000) + 500.000 = 7.520.000 đồng`

[RESULT: 7.520.000 đồng]
```

**Link trò chuyện:** https://share.gemini.google/VPx6q159LQjj

### b) Kiểm tra kết quả AI

Không biết

## 4.4. Dây chuyền xử lý khiếu nại – kết quả Trạm 1

**KET QUA AI**

```text
```json
{
  "loai_su_co": "sai_phong",
  "so_khach": 3,
  "so_ca_bi_anh_huong": 2,
  "tom_tat": "Khách mua gói TT bị xếp sai sang phòng học thường thiếu đèn livestream và ồn trong 2 ca đầu."
}

```
```

**Link trò chuyện:**https://share.gemini.google/nlSU0CBLA2XT

## 4.5. Prompt chấm bài theo Rubric

**KET QUA AI**

```text
Dưới đây là kết quả kiểm chứng số liệu và bảng chấm điểm câu trả lời của nhân viên tư vấn tập sự dựa trên thông tin chuẩn `<tt>` và tiêu chí `<tc>`:

| Tiêu chí | Điểm | Minh chứng | Đề xuất sửa |
| --- | --- | --- | --- |
| **Đúng thông tin** (50%) | **0 / 5,0** | • **Câu lỗi:** *"Gói TikTok Affiliate bên mình giá chỉ 1.200.000đ/người thôi..."*<br>

<br>**Lý do sai:** Báo sai giá gói (1.200.000đ thay vì 1.500.000 đồng/Creator chính theo thông tin chuẩn).<br>

<br>

<br>• **Câu lỗi:** *"Bạn báo huỷ trước 5 ngày thì được hoàn lại đủ 100% tiền nha..."*<br>

<br>**Lý do sai:** Báo sai chính sách hoàn tiền. Hủy trước 5 ngày thuộc khung từ 3 đến 6 ngày nên chỉ được hoàn **50%**, không phải 100% (hoàn 100% áp dụng khi hủy trước từ 7 ngày trở lên). | • *"Gói TikTok Affiliate bên mình có mức phí là 1.500.000 đồng cho mỗi Creator chính ạ."*<br>

<br>

<br>• *"Theo chính sách của trung tâm, nếu bạn báo hủy trước ngày bắt đầu từ 7 ngày trở lên sẽ được hoàn 100%, từ 3 đến 6 ngày sẽ được hoàn 50%, và dưới 3 ngày sẽ không hoàn tiền ạ."* |
| **Đầy đủ** (30%) | **0 / 3,0** | • **Câu lỗi:** *(Không có nội dung phản hồi đủ hai câu hỏi của khách hàng và không có lời mời cung cấp thông tin đăng ký trong toàn bộ câu trả lời)*<br>

<br>**Lý do sai:** Thiếu các phần thông tin/điều hướng bắt buộc theo tiêu chí đầy đủ: chưa đáp ứng đủ hai câu hỏi của khách hàng và chưa mời khách hàng cung cấp **ngày đợt thực chiến** cũng như **số lượng suất muốn đăng ký**. | • *"Để hỗ trợ bạn đăng ký chính xác nhất, bạn vui lòng cho mình biết **ngày đợt thực chiến** bạn dự kiến tham gia và **số lượng suất** bạn muốn đăng ký nhé."* |
| **Giọng điệu** (20%) | **0 / 2,0** | • **Câu lỗi:** *"Dạ hello bạn nha!"*<br>

<br>**Lý do sai:** Cách chào hỏi thiếu chuyên nghiệp, pha trộn từ ngữ suồng sã ("hello", "nha").<br>

<br>

<br>• **Câu lỗi:** *"...đăng ký xong gắn link là nổ đơn hoa hồng trăm triệu luôn ạ."*<br>

<br>**Lý do sai:** Cam kết/gợi ý doanh thu, hoa hồng ảo không có cơ sở đảm bảo, gây hiểu lầm và làm giảm uy tín trung tâm.<br>

<br>

<br>• **Câu lỗi:** *"...cứ chốt lẹ kẻo hết slot nè!"*<br>

<br>**Lý do sai:** Dùng từ ngữ suồng sã, thúc ép ("chốt lẹ", "slot", "nè"), không phù hợp với phong cách tư vấn chuyên nghiệp. | • *"Dạ xin chào bạn, cảm ơn bạn đã quan tâm đến chương trình tại VietAffiliate."*<br>

<br>

<br>• *"Tham gia khóa học sẽ giúp bạn nắm vững quy trình và kỹ năng triển khai TikTok Affiliate hiệu quả, còn kết quả kinh doanh thực tế sẽ phụ thuộc vào cách triển khai và nỗ lực của từng cá nhân ạ."*<br>

<br>

<br>• *"Số lượng chỗ cho mỗi đợt có giới hạn nên bạn cân nhắc đăng ký sớm để giữ chỗ nhé."* |
| **Tổng điểm** | **0 / 10** | — | — |
```

**Link trò chuyện:** https://share.gemini.google/PLb2z3Jz9tVz
