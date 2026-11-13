# Bài 2: Nhận diện 3 loại dữ liệu thuộc "Vùng cấm tuyệt đối" khi sử dụng AI**

## 3. Ràng buộc an toàn**

Bẫy: Lan cho rằng Web UI cá nhân là riêng tư, nhưng theo điều khoản của Public LLM, dữ liệu này sẽ bị lưu trữ và dùng để huấn luyện lại (Re-training) mô hình AI, khiến PII bị lọt lướt ra toàn thế giới.

## 4. Yêu cầu đầu ra**

### **Phần 1 (Rà soát & Phân loại):** Dựa vào Mục 2.1 Lesson 02, liệt kê 3 loại dữ liệu thuộc "Vùng cấm tuyệt đối". Đối chiếu với Bảng dữ liệu trên và chỉ ra chính xác từng trường thông tin vi phạm nhóm dữ liệu nào.

**3 nhóm dữ liệu thuộc “Vùng cấm tuyệt đối”**

Nhóm 1: *PII (thông tin định danh cá nhân)* gồm	Họ tên, số điện thoại, số căn cước, địa chỉ nhà

Nhóm 2: *Dữ liệu tài chính, thẻ ngân hàng* gồm	Số thẻ, mã PIN/CVV, hạn mức tín dụng, số tài khoản

Nhóm 3: *Dữ liệu mật nội bộ doanh nghiệp* gồm	Danh sách khách hàng VIP, ghi chú VIP, dữ liệu kinh doanh, mật khẩu, API key

| Trường dữ liệu | Ví dụ trong bảng | Nhóm vi phạm | Mức độ |
|---|---|---|---|
| Họ và tên | Nguyễn Thị Mai, Trần Văn Hùng, Lê Hoàng Nam | Nhóm 1: PII | Cao |
| Số điện thoại | 0912.345.678, 0988.777.666, 0903.111.222 | Nhóm 1: PII | Cao |
| Địa chỉ nhà | 123 Nguyễn Trãi, Biệt thự 15 Thảo Điền, 45 Lê Lợi | Nhóm 1: PII | Cao | 
| Số thẻ ATM | 9704.1234.5678.9012 | Nhóm 2: Tài chính | Cực cao | Nguy cơ gian lận, đánh cắp tiền |
| Hạn mức tín dụng | 500.000.000 VNĐ | Nhóm 2: Tài chính | Cao |
| Mã PIN/CVV | 888 (tài khoản MartX Pay) | Nhóm 2: Tài chính | Cực kỳ nghiêm trọng |
| Ghi chú VIP, danh sách khách VIP | Cột "Ghi chú VIP", cả file Excel | Nhóm 3: Mật nội bộ | Cao |


### **Phần 2 (Xử lý sự cố):** Đánh giá nguy cơ pháp lý MartX phải chịu và đề xuất 3 bước xử lý sự cố khẩn cấp cho Phòng IT.

-MartX đối mặt rủi ro vi phạm quy định bảo vệ dữ liệu cá nhân (Nghị định 13/2023/NĐ-CP, Luật Bảo vệ dữ liệu cá nhân) do để nhân viên chuyển PII và dữ liệu tài chính của khách VIP cho nhà cung cấp AI công cộng khi chưa có sự đồng ý của chủ thể. Hậu quả có thể gồm xử phạt hành chính hoặc hình sự, nghĩa vụ thông báo cơ quan chức năng trong thời hạn luật định, bồi thường dân sự và suy giảm uy tín thương hiệu. Việc lộ mã PIN/CVV làm mức độ nghiêm trọng tăng cao.

**3 bước xử lí sự cố khẩn cấp cho phòng IT**
1. Ngăn chặn và thu thập bằng chứng (trong vài giờ đầu) Khoanh vùng, giảm thiểu phát tán
2. Đánh giá thiệt hại và báo cáo (trong 24 đến 72 giờ)Xác định phạm vi, báo cáo
3. Khắc phục và phòng ngừa Thông báo khách, chặn tái diễn
