
# Lab: Username enumeration via different responses

Ở bài lab này chúng ta được cho 2 danh sách , một danh sách là tên đăng nhập còn lại là một danh sách mật khẩu chúng ta sẽ dùng burp để dò tên đăng nhập ( hay còn gọi là tấn công vét cạn ). 

Ở phần loggin chúng ta đăng nhập một tài khoản  bất kỳ để  lấy gói request và cho nó vào intruder. 

<img width="1645" height="757" alt="image1" src="https://github.com/user-attachments/assets/723d566f-21e0-468b-81f7-7f9ceab6df88" />

<img width="1909" height="1038" alt="image6" src="https://github.com/user-attachments/assets/9f16a17a-21d6-448c-8c50-3c031d872f6b" />


Ở đây chúng ta sẽ dùng tính năng của intruder , ở chế độ snipper nhé. 

Đầu tiên hãy cho phần username mà chúng ta đã có và cho chúng vào.

<img width="1903" height="881" alt="image7" src="https://github.com/user-attachments/assets/dff07c1a-e3ab-4f70-ad2b-c57395fe8e8c" />

Bôi đen dòng username của chúng ta và sau đó nhấp vào ADD $  và copy list username mà bài tập cho ta sau đó sẽ nhấp vào start attack. Ở đây chúng ta sẽ thực hiện dò tài khoản trước sau đó sẽ thực hiện  dò mật khẩu. 

<img width="1877" height="1068" alt="image5" src="https://github.com/user-attachments/assets/5f1430a0-0d4b-404a-be40-146a9fa2259e" />

Vậy thì sau khi ấn start attack chúng ta có thể thấy nó hiện ra một bản hãy để ý xem 

<img width="1881" height="1021" alt="image3" src="https://github.com/user-attachments/assets/b9409c91-3e9c-458e-9e39-55a194cbdee2" />


Ở đây chúng ta có thể thấy username = application là nơi chúng ta có Length khác với các payload khác. Và kéo trong phần reponse chúng ta có thể thấy ở warning không có ghi incorrect username → vậy là chúng ta đã dò ra username của bài này , còn mật khẩu nữa. 

Bây giờ bước tiếp theo sẽ giống như bước dò username nhưng ở đây chúng ta dò password chứ không phải username ( hãy nhớ là để username là tên application và cho password ADD $ sau đó thêm hàng loạt payload mà để bài cho để tấn công burp-force ). 

Sau khi dò quét chúng ta sẽ thấy, 

<img width="1853" height="986" alt="image4" src="https://github.com/user-attachments/assets/ef273484-fc92-42e6-8a38-e38489771a54" />

Ở đây phần length chúng ta có một payload có tên computer trả về length khác với cái gói khác, ấn vào thì thấy reponse trả về giá trị 302 → Chuyển hướng , chúng ta nghi ngờ đây là user cần tìm của bài lab và đăng nhập bằng tài khoản = application và mật khẩu = computer vào bài lab. 

<img width="1680" height="790" alt="image2" src="https://github.com/user-attachments/assets/cd4b96f3-fd29-4174-bd0b-2fe66e1bc7d4" />

Tuỵt, ở đây chúng ta đã hoàn thành bài lab này. 
