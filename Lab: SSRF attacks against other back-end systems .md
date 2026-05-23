# SSRF attacks against other back-end systems

Bài lap này chúng ta sẽ vào admin và xóa user. Khi vào check số lượng sản phẩm thì bên burpsuite chúng ta có thể thấy một request tới máy chủ để check số lượng sản phẩm còn sót lại ở đây. 

<img width="1299" height="792" alt="1" src="https://github.com/user-attachments/assets/d0dbb31b-d6e3-4bac-9d51-82256d03a05f" />

Ok, vậy ở đây chúng ta có api gọi tới  ‘’’ http://192.168.0.1:8080/product/stock/check?productId=2&storeId=1 ‘’’ 

Để kiểm tra số lượng sản phẩm.  Theo bài lab thì chúng ta có dãy ip ở 192.168.0.X   ta sẽ quét để vào được bảng quản admin. 

<img width="1898" height="818" alt="2" src="https://github.com/user-attachments/assets/5b7f7088-db20-4140-a312-48b5dde6b3f6" />

Ở đây chúng ta sẽ sử dụng dãy ip là 192.168.0.x để quét từ 1 -> 255 để kiếm trang của admin , ấn start attack để bắt đầu quét bằng burp. Khi nào status hiện lên là 200 thì chúng ta sẽ sử dụng ip đó để đăng nhập vào trang của admin để thực hiện yêu cầu bài làm. 

<img width="1860" height="1043" alt="3" src="https://github.com/user-attachments/assets/19981593-55b0-4ca6-a7ad-2c8fc4a76f95" />

Sau một thời gian chờ chúng ta đã chờ được tín hiệu 200 và đã thấy địa chỉ ip của trang admin là 192.168.0.200.   Sau khi đăng nhập được vào ta sẽ thực hiện yêu cầu bài tập. 

<img width="1525" height="1146" alt="4" src="https://github.com/user-attachments/assets/2d80232e-e5d1-4bd9-bab1-898b5afa429a" />
 
Ở đây chúng ta có thể thấy user cần xóa và chỉ cần quay lại burp  nhập tên user muốn xóa và chúng ta sẽ thực hiện thành công bài tập này. 

<img width="1466" height="547" alt="5" src="https://github.com/user-attachments/assets/f43d46ae-4b4b-4255-9507-58c52a5fbae0" />

Thành công, chúng ta đã thực hiện xong bài lab này. 


