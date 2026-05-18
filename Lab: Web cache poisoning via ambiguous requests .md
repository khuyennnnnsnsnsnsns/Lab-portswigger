# Lab: Web cache poisoning via ambiguous requests
## Lý thuyết 
Thông thường 1 request chỉ được có một tiêu đề host, tuy nhiên trong bài lab này chúng ta sẽ thực hiện 2 tiêu đề host.

Host đầu tiên ( ở phần front-end)   xác thực xem request này có hợp lệ hay không sau đó dùng để tạo cache key ( mã nhận diện để lưu bộ nhớ đệm). Host thứ 2 khi hệ thống trả về giao diện hệ thống lại đọc host 2 (backend), khi thấy host 2 nó lầm tưởng đây là domain hệ thống nên sẽ dùng để tạo đường dẫn tuyệt đối. 

→ khi người dùng truy cập trang chủ họ  sẽ tải file mã độc thay vì file sạch vì hệ thống cache đã lưu lại trang chủ đã bị sửa. 

## Thực hiện bài lab: 
## Phân tích hành vi của request trang chủ 
Đầu tiên chúng ta sẽ tải lại trang , và  tìm get để send to repeater 

<img width="1960" height="422" alt="1" src="https://github.com/user-attachments/assets/5286a31a-4861-46d6-9caa-777ff59f4959" />

## Thử nghiệm để tìm lỗi 
Sau đó chúng ta sẽ vào repeater, vì trang web có bật bộ nhớ đệm ( cache) nên khi chúng ta request lại đường link đó thì nó sẽ dính cache cũ của chính mình nên vì vậy ở đây hãy thay      GET/ HTTP/1.1 → GET/?cb=1 HTTP/1.1 ( hoặc thay cb= abc tùy ý ). Mỗi lần thay mới thì nó sẽ ép backend sử lý lại vì nó coi  đây là  một request mới.

<img width="1621" height="973" alt="2" src="https://github.com/user-attachments/assets/a733fa53-3f4b-400f-99b6-d72be4e02961" />

Sau đó chúng ta hãy thêm một Host khác ngay dưới Host của chúng ta. Ở đây tôi sẽ thử  ‘’’ Host: khuyen123 ‘’’ và ấn ‘’’ SEND ‘’’ để xem phần reponse. 

<img width="1622" height="871" alt="3" src="https://github.com/user-attachments/assets/9d360bc9-9c98-4414-b3ae-ce8e4c843676" />

Quan sát nội dung bên ‘’’ Response ‘’’  chúng ta có thể thấy ở phần HTML,  domain khuyen123 của tôi đã được chèn vào trực tiếp link nạp thẻ 

 ‘’’    <script type="text/javascript" src="//khuyen123/resources/js/tracking.js">     ‘’’ 

→ Điều này xác nhận ứng dụng bị lỗi 

## Chuẩn bị tệp mã độc 
Trên giao diện của bài lab, ấn vào  “ go to exploit server “ 

<img width="1327" height="432" alt="4" src="https://github.com/user-attachments/assets/9593bb80-46e9-46c2-b6d5-1113701fba13" />

Tại mục File path, nhập chính xác đường dẫn mà ứng dụng gọi: /resources/js/tracking.js. 

Tại mục Body, nhập đoạn mã JavaScript để chiếm quyền hoặc kích hoạt alert theo yêu cầu bài lab:  ‘’’ alert(document.cookie) ‘’’

<img width="1293" height="1096" alt="5" src="https://github.com/user-attachments/assets/d61f9e7d-25be-4590-b637-244dfb4b95e0" />

## Đầu độc bộ nhớ đệm 

Sau khi nhập chúng ta sẽ quay lại Repeater thay thế host 2 bằng domain máy chủ độc hại. Sau đó send liên tục để thấy phần x-cache : hit → lúc này chúng ta đã thành công. 

<img width="1093" height="717" alt="6" src="https://github.com/user-attachments/assets/423a2ccb-5ea7-4df1-ac6a-1e73291a9161" />
  
Để kiểm tra lại chúng ta copy url mở tab khác ra thì nó sẽ hiện hộp thoại cảnh báo lên. 

<img width="1283" height="330" alt="7" src="https://github.com/user-attachments/assets/c3d7c9c3-31d8-4918-aaf6-241713399672" />


## Thực hành tấn công 
Đầu tiên chúng ta xóa tham số cache buster đưa nó về nguyên bản Get /http/1.1  . Sau đó ấn SEND liên tục để đè phản hồi độc hại vào đúng phân vùng bộ nhớ đệm của trang chủ thực tế mà không cần tham số.Khi hệ thống ghi nhận Cache Hit thành công cho trang chủ sạch, hệ thống giả lập nạn nhân đang lướt web tự động truy cập vào trang chủ sẽ ngay lập tức thực thi file JS độc của bạn. 

<img width="1933" height="990" alt="8" src="https://github.com/user-attachments/assets/922b10b4-cc56-4972-b68c-54158ec1231c" />





