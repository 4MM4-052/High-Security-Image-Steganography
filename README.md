# High-Security-Image-Steganography
MÔ HÌNH ẨN ẢNH CHẤT LƯỢNG CAO DỰA TRÊN MẠNG MÃ HÓA - GIẢI MÃ &amp; MÃ HÓA HỖN LOẠN LOGISTIC 2D 

## 🔹 GIỚI THIỆU

Đây là một **mô hình giấu ảnh trong ảnh chất lượng cao**, được đề xuất kết hợp giữa:

- **Mạng học sâu Encoder–Decoder**
- **Thuật toán mã hóa hỗn loạn 2D Logistic**

**Mục tiêu chính** của hệ thống là:

- Cung cấp phương pháp **an toàn và hiệu quả** để **che giấu và truyền tải thông tin mật** trong ảnh.
- Không làm ảnh hưởng đến **chất lượng hiển thị**.
- Khó bị phát hiện bằng **mắt thường** hoặc các công cụ phân tích **steganalysis**.

Hệ thống hoạt động **khép kín**, bao gồm **mã hóa ảnh bí mật, giấu tin, trích xuất và giải mã**, giúp người dùng xử lý toàn bộ quy trình **bảo mật và trực quan**.


## 🔹 KIẾN TRÚC HỆ THỐNG

Hệ thống gồm **hai thành phần chính**:  

### 1. Chaotic Encryption / Decryption

- **Mục đích:** mã hóa ảnh bí mật để tăng **tính ngẫu nhiên** và **bảo mật** trước khi giấu tin.
- **Thuật toán:** 2D Logistic Chaotic Map
  - Xáo trộn giá trị pixel theo quy luật **phi tuyến**, làm dữ liệu **khó dự đoán** và **khó phục hồi** nếu không có khóa giải mã.
- **Tăng cường bảo mật:** kết hợp với **mã hóa khối** như:
  - **AES**: Mã hóa nhanh, mạnh, bảo mật cao.
  - **Blowfish**: Nhẹ hơn AES, linh hoạt xử lý ảnh hoặc văn bản.

> Kết hợp giữa **chaotic encryption** và **block cipher** tạo ra **đa lớp bảo vệ**, khiến việc phân tích hoặc phá mã trở nên khó khăn.

---

### 2. Image Steganography

Gồm **ba mạng chính**:

####  ⭐ Generator Network (Encoder)

- Nhúng **ảnh bí mật đã mã hóa** vào **ảnh bìa (cover image)** để tạo ra **stego image**.  
- Giúp **duy trì chất lượng ảnh** gần như nguyên gốc, khó bị phát hiện.

<p align="center">
  <img width="600" height="700" alt="image" src="https://github.com/user-attachments/assets/d8ff7b3d-a893-4fc2-aed3-b58ac5bad1c1" />

</p>

####  ⭐ Extraction Network (Decoder)

- Trích xuất và khôi phục lại **ảnh bí mật** từ **stego image**.

<p align="center">
  <img width="600" height="700" alt="image" src="https://github.com/user-attachments/assets/d1e46416-c2d7-4f78-94d7-86d32f67e24b" />

</p>

####  ⭐ Discriminator Network

- Phân biệt giữa **ảnh bìa** và **stego image**.
- Hỗ trợ **adversarial learning**, giúp mô hình học cách **giấu tin tự nhiên**.

---

### 🔁 Quy trình tổng thể

Hai thành phần trên hoạt động liên kết trong cùng một hệ thống, tạo nên mô hình giấu tin chất lượng cao vừa đảm bảo:

- **Tính ẩn giấu mạnh mẽ**
- **Chất lượng hình ảnh tối ưu**

<p align="center">
  <img width="950" height="350" alt="image" src="https://github.com/user-attachments/assets/4da25a77-b8ce-4fc5-9328-28b79179d082" />

</p>

**Quy trình chi tiết:**

1. **Mã hóa ảnh bí mật** bằng 2D Logistic Chaotic Map và (tùy chọn) AES / Blowfish.
2. **Nhúng ảnh bí mật** vào ảnh bìa bằng Generator Network.
3. **Trích xuất ảnh bí mật** bằng Extraction Network.
4. **Giải mã** để thu lại ảnh bí mật gốc.
   

## 🔹 CHỨC NĂNG CHÍNH

1. **Giấu ảnh bí mật vào ảnh bìa**
   - Chọn ảnh bí mật và ảnh bìa.
   - Nhúng ảnh bí mật để tạo ra **stego image**.
   - Ảnh sau khi giấu có **chất lượng gần như không đổi**.

2. **Trích xuất và khôi phục ảnh bí mật**
   - Trích xuất ảnh từ **stego image**.
   - Giải mã để thu lại ảnh gốc.

3. **Mã hóa ảnh stego (tùy chọn)**
   - Dùng AES hoặc Blowfish để tăng cường bảo mật.
   - Hệ thống sinh **Encryption Key Table** lưu thông tin mã hóa.

4. **Giải mã ảnh stego**
   - Sử dụng key để giải mã stego image.
   - Trích xuất ảnh bí mật từ stego image.
  
## 🔹 GIAO DIỆN  

1. **Tính năng ẩn ảnh**
   1. **Ẩn ảnh kết hợp kỹ thuật mã hóa hỗn loạn 2D Logistic**
      
      <img width="796" height="375" alt="image" src="https://github.com/user-attachments/assets/038b8f09-3fd4-462f-b72d-64d0ad5461bc" />

   3. **Ẩn ảnh bằng Deep**
      
      <img width="806" height="361" alt="image" src="https://github.com/user-attachments/assets/8c486d16-b3d3-4afa-a109-9a6285c61173" />
    
2. **Tính năng trích xuất ảnh secret**
   1. **Trích xuất ảnh secret kết hợp giải mã 2D Logistic**
      
      <img width="779" height="405" alt="image" src="https://github.com/user-attachments/assets/d7ddefb1-f438-4f7f-a2a5-788995c6bb33" />

   3. **Trích xuất ảnh secret bằng Deep**
      
      <img width="757" height="377" alt="image" src="https://github.com/user-attachments/assets/25d07af5-618e-44a9-aa3d-11d1f14114fc" />

3. **Tính năng mã hóa - giải mã ảnh bằng AES hoặc Blowfish**
  1. **Mã hóa ảnh bằng AES**
     
     <img width="818" height="395" alt="image" src="https://github.com/user-attachments/assets/8bdef00a-0cff-4e1d-ae3c-d76721d1e4b6" />

  3. **Giải mã ảnh bằng AES**
     
     <img width="843" height="408" alt="image" src="https://github.com/user-attachments/assets/38ee2f05-1cd1-460f-b556-6f1c7bd536a8" />


         

