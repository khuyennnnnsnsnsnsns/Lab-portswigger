<img width="1522" height="845" alt="image" src="https://github.com/user-attachments/assets/3c0f8335-d4c1-4dfa-96b3-0a51968b19ad" />

Ở đây chúng ta đang vào bài lab 
UNION attack: lợi dụng truy vấn hiện có để đưa kết quả từ một truy vấn khác vào phản hồi của website.

Ở đây ta sẽ làm một cái ví dụ cụ thể hơn bài lab này : 

http://shop.example/products?category=Gifts 

Như url ở trên chúng ta biết là nó request sql là: Gifts

có thể câu truy vấn sql sẽ là 

<img width="500" height="152" alt="image" src="https://github.com/user-attachments/assets/148ca839-f4fa-4d2c-8985-04ab92fb5d68" />

?category=Gifts' UNION SELECT NULL,NULL,email FROM users-- -

Nếu chúng ta biết giá trị và bảng thì chúng ta có thể selcect được giá trị chúng ta muốn là email from . 
