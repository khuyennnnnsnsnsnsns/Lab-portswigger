<img width="1917" height="988" alt="image" src="https://github.com/user-attachments/assets/ed592697-4e1a-4cd7-b645-0fec96d49645" />

Ở lab này chúng ta sẽ dùng union , chúng ta đã biết union là cách làm cho 2 câu lệnh chạy đồng thời nhau .

Union là lệnh xuất ra khi các kết quả như nhau ra một table:

- yc 1 : 2 table phải cùng số cột

- yc2 : kiểu dữ liệu 2 table tương ứng ( table 1 là số thì table 2 cũng phải là số )

UNION SELECT: Lệnh SQL dùng để gộp kết quả của câu truy vấn gốc với kết quả từ truy vấn của người tấn công. Điều kiện bắt buộc để dùng lệnh này là cả hai truy vấn phải có cùng số lượng cột.

NULL,NULL,NULL: Người tấn công đang "đoán" rằng bảng kết quả có 3 cột. Việc dùng NULL là thủ thuật phổ biến nhất vì NULL có thể đại diện cho bất kỳ kiểu dữ liệu nào (chữ, số...), giúp tránh lỗi xung đột kiểu dữ liệu. Nếu trang web tải bình thường, chứng tỏ đúng là có 3 cột. Nếu web báo lỗi (ví dụ: Internal Server Error), họ sẽ đổi thành 2 chữ NULL hoặc 4 chữ NULL cho đến khi trang hết lỗi.

' UNION SELECT NULL FROM DUAL--
