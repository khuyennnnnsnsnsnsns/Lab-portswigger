# Lab: Basic SSRF against the local server 

sever side request forgery là tấn công giả mạo yêu cầu phía máy chủ đây là cách tấn công khiến máy chủ thực hiện đến một vị trí mà hacker mong muốn. 

Thực hiện bài lab: 

Chúng ta phải kết nối vào phòng lab và ấn vào một món đồ bất kì và xem số lượng còn tồn kho . 

<img width="1902" height="982" alt="1" src="https://github.com/user-attachments/assets/c480a5b8-fd05-4c1c-8600-4b128dd81c79" />

Đây là ngay sau khi ấn kiểm tra hàng trong khu chúng ta sẽ thấy ứng dụng truyền một url để kiếm tra xem hàng còn bao nhiêu ở phía máy chủ. Chúng ta có thể lợi dụng những lổ hổng 

này để khai thác SSRF. 

Vậy để thực hiện truy vấn đến máy chủ thì chúng ta dùng http://localhost/admin để thử xem nó có giúp chúng ta đăng nhập vào tài khoản admin không 

<img width="1583" height="705" alt="2" src="https://github.com/user-attachments/assets/b8353879-2100-46a8-a6da-ac17b555ff6e" />

Dùng cyberchef để mã hóa đường truyền sau đó thay vào url để thử.

<img width="1483" height="802" alt="3" src="https://github.com/user-attachments/assets/4cf2f2e5-871a-435e-9e15-39da3792c00e" />


Vậy là chúng ta đã truy cập được vào trang admin rồi giờ hãy làm theo mục tiêu bài tập là xóa user “ carlos “ 

<img width="1502" height="976" alt="4" src="https://github.com/user-attachments/assets/adb3fff2-6430-4415-84a2-d862ef6f6da6" />

Ở phần response chúng ta ấn vào sẽ thấy Admin panel ở bảng User có 2 user và có user mục tiêu chúng ta muốn xóa giờ chúng ta sẽ sang cyberchef để truy vấn vào mục user và delete carlos 

<img width="1351" height="832" alt="5" src="https://github.com/user-attachments/assets/9f45d4fc-77f2-49f6-ba30-636f8a0dc875" />


Ở đây chúng ta đã thấy được đường dẫn để xóa user tên là carlos rồi sau đó hãy lấy đường dẫn này và cho nó vào cyberchef mã hóa sau đó sử dụng burp suite để send lại xem. 

<img width="1513" height="772" alt="6" src="https://github.com/user-attachments/assets/b075726a-910a-46d1-b702-1ceada256a2b" />

Ok chúng ta đã thực hiện xong bài lab này. 


