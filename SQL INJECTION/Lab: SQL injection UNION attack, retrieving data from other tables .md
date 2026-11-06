' UNION SELECT username, password FROM users--


Nếu truy vấn ban đầu của ta là trả về 2 cột , cả 2 đều chứa dạng chuỗi . Để thực hiện được union này chúng ta cần biết có một table name users với 2 cột là username và password 

To solve the lab, perform a SQL injection UNION attack that retrieves all usernames and passwords, and use the information to log in as the administrator user.

<img width="1631" height="927" alt="image" src="https://github.com/user-attachments/assets/9ca34671-df75-4c92-b7d2-b6ebb0f3f798" />


<img width="1646" height="972" alt="image" src="https://github.com/user-attachments/assets/f1b3691c-0f35-4e09-8db0-bd5c0c2c2f3b" />


B1: Chungs ta sẽ dò xem là chúng ta có bao nhiêu cột 

B2: chúng ta biết nó có 2 cột , và khi truy vấn 2 cột này đề đã cho kiểu data là username và password từ table users nên chúng ta sẽ selct và sẽ in data admin ra . Sau đó chúng ta sẽ copy username password và cho vào . vậy là done lab
