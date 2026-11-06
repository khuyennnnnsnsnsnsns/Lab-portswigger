# Truy xuất nhiều giá trị trong cùng một cột

' UNION SELECT username || '~' || password FROM users--

Đây là một ví dụ của tấn công truy xuất nhiều giá trị cùng một cột. || '~' ||

đây là tính năng của oracle cho phép tối các data với nhau 

Nếu chúng ta dùng thì khi in ra nó sẽ in ra username~password : giống như union chưa tìm kiếm được sự khấc biết , cũng không phải là một kiểu tấn công khác union nhưng đây cũng là một cách chúng ta có thể hiểu là nó giống union nhưng khi in ra tuy không trả ra 2 cột thì nó trả về 1 cột nó phù hợp nếu mình muốn làm nó trong một cột 

<img width="1437" height="407" alt="image" src="https://github.com/user-attachments/assets/cde06b0a-7d2f-4fce-a675-63510e121b47" />
