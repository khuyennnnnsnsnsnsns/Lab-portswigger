# Lab: SQL injection with filter bypass via XML encoding

Bài lab này chúng ta sẽ thực hiện SQLi, đầu tiên chúng ta vào bài lab, thực hiện check stock sản phẩm , và gửi cái thông tin request vào repeater 

<img width="1912" height="1123" alt="image4" src="https://github.com/user-attachments/assets/f3c70f69-f045-4e6b-ae0a-0a9765c94421" />

Trong phần hint của sản phẩm chúng ta có thêm waf ( web application firewall ) để chặn tấn công sql injection . Để kiểm tra ở đây chúng ta thử select.

<img width="1475" height="850" alt="image2" src="https://github.com/user-attachments/assets/114f9b77-defc-4302-95b8-f9827a7d68b3" />

Ở đây bài cho chúng ta một bảng users table thì chúng ta thử select * from users tables nhưng bị chặn, thử các cách mà trong mấy bài lab sqli chúng ta đã thử nhưng không được. 

<img width="1472" height="877" alt="image1" src="https://github.com/user-attachments/assets/f3efd874-3618-4558-9d00-53e1414cd347" />


Ở đây chúng ta sẽ chèn mã độc sqli ( sử dụng mã hóa html entities để có thể bypass qua waf chặn sqli )  ở đây , sẽ sử dụng là ‘’’union select username from users ‘’’ và chúng ta sẽ list ra hết tất cả username trong đó chúng ta thấy có username là administrator . Sau đó để tìm được password của admin thì chúng ta dùng tương tư ‘’’ union select password from users where username = ‘administrator’ ‘’’ chúng ta sẽ khai thác được mật khẩu admin như trên .  Sau khi có được password chúng ta đem nó sang nơi đăng nhập và đăng nhập vào tài khoản admin . Vậy chúng ta đã hoàn thành bài lab.

<img width="1919" height="948" alt="image3" src="https://github.com/user-attachments/assets/94e7e407-fcae-420b-96e4-ce3dd7a05761" />

