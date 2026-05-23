# Lab: SSRF with blacklist-based input filter

Sever side request forgery là tấn công giả mạo yêu cầu phía máy chủ đây là cách tấn công khiến máy chủ thực hiện đến một vị trí mà hacker mong muốn. 

Bài lab này đã có triển khai 2 lớp phòng chống SSRF, chúng ta sẽ thực hiện theo yêu cầu của bài lab. 

Đầu tiên chúng ta vào bài lab thử gọi api đến,  hãy thử địa chỉ 127.0.0.1 thử xem có bị chặn hay không. 

<img width="1515" height="735" alt="1" src="https://github.com/user-attachments/assets/37f3c26c-a883-4133-868f-830922f5bd32" />

Vẫn bị chặn thử chuyển đổi ip sang decimal , sang dạng bát phân , hoặc dạng rút gọn thử 127.0.0.1 →  127.1 . Sau khi thử thì chúng ta đã vào được. 

<img width="1698" height="1080" alt="2" src="https://github.com/user-attachments/assets/38abaa91-43a8-4697-9fe8-3980d9d7122f" />

Sau khi rút gọn ip thì chúng ta đã vào được , bây giờ hãy vào trang admin bằng cách mã hóa nó đi. 

<img width="1918" height="888" alt="3" src="https://github.com/user-attachments/assets/7711a208-2b6b-4827-8809-d7ced0d71296" />

Sau khi thử encode url thì encode 2 lần chúng ta sẽ vào được trang admin. Bây giờ hãy thực hiện xóa user như các bài SSRF trước là chúng ta sẽ làm được. 

<img width="1588" height="902" alt="4" src="https://github.com/user-attachments/assets/37460eed-fd66-4bbd-8fad-06e5da8568bc" />

Vậy chúng ta đã thực hiện được bài lab này rồi. 



