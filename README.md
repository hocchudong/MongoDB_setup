# MongoDB_setup
## Giới thiệu
Đây là một cơ sở dữ liệu NoSQL thuộc loại cơ sở dữ liệu hướng văn bản mã nguồn mở, có hiệu năng, tính sẵn có và tính mở rộng cao được cung cấp và hổ trợ bởi 10gen. MongoDB được 10gen phát triển từ năm 2007, đến năm 2009, MongoDB trở thành một sản phẩm mã nguồn mở có giấy phép AGPL. MongoDB được viết bằng ngôn ngữ C++. MongoDB lưu trữ dữ liệu dạng BSON. Không giống như các cơ sở dữ liệu quan hệ lưu dữ cấu trúc dữ liệu theo các bảng, MongoDB lưu trữ cấu trúc dữ liệu thành văn bản dựa JSON với mô hình động (gọi là BSON) khiến cho việc tích hợp dữ liệu cho các ứng dụng trở nên dễ dàng và nhanh hơn.Với mục tiêu là kết hợp các điểm mạnh của mô hình khóa – giá trị (nhanh mà tính mở rộng cao) với mô hình dữ liệu quan hệ (giàu chức năng).

Mục tiêu chính của Mongo là giữ lại các thuộc tính thân thiện của SQL. Do đó các câu truy vấn khá giống với SQL nên MongoDB khá thích hợp cho các lập trình viên đã quen với ngôn ngữ truy vấn SQL. MongoDB có một khối lượng tính năng lớn và hiệu năng cao. Với các loại dữ liệu phong phú, nhiều truy vấn và việc giảm thời gian phát triển trong việc mô hình hóa các đối tượng.
MongoDB được sử dụng tốt nhất với nhu cầu cần truy vấn động, cần tốc độ nhanh cho một cơ sở dữ liệu lớn vì MongoDB ngoài tốc độ đọc nhanh ra thì tốc độ ghi của nó rất nhanh.
MongoDB hỗ trợ việc tìm theo trường, khoảng kết quả tìm và tìm theo cú pháp. Các truy vấn có thể trả về các trường được qui định trong văn bản và cũng có thể bao gồm các hàm Javascript mà người dùng chưa định nghĩa. Cũng giống như các cơ sở dữ liệu quan hệ, bất cứ một trường nào trong MongoDB đều được đánh chỉ mục. MongoDB còn có hổ trợ theo mô hình chủ - tớ (master - slave), mảnh, vùng dữ liệu (Sharding).

MongoDB sử dụng một quá trình xử lý để xử lý các yêu cầu về dữ liệu, quản lý định dạng dữ liệu, thực hiện các hoạt động quản lý bên dưới là mongod, đây là trình xử lý chính. Trong việc mở rộng theo chiều ngang sử dụng mô hình mảnh lưu trữ, MongoDB cung cấp dịch vụ xử lý các truy vấn từ tầng ứng dụng, xác định vị trí dữ liệu trong cụm các node phân mảnh được gọi là mongos


## Cài đặt

Để cài đặt phiên bản ổn định mới nhất của MongoDB:
```sh
$ sudo apt-get install -y mongodb-org
```
Celometer sẽ giám sát từng máy ảo trong OpenStack và lấy mẫu về hệ thống theo định kỳ trong một khoảng thời gian được khai báo trong cấu hình. Đây là dịch vụ phục vụ lưu log và tính cước cho hệ thống vì vậy cần sao lưu dữ liệu dự phòng. Dữ liệu Ceilometer thu thập về sẽ lưu vào cơ sở dữ liệu là MongoDb. 
Tạo bản sao lưu dữ liệu:
```sh
mongodump --host mongodb.example.net --port 27017
```
 
 <img src=http://i.imgur.com/pvu8kCG.png width="80%" height="80%" border="1">
 
Trong câu lệnh mongodb.example.net là máy server chứa database MongoDB. Bản sao dữ liệu sẽ được sinh ngay tại thư mục hiện tại, để lưu bản sao về thư mục định nghĩa trước ta thêm tham số –out như sau
```sh
mongodump --host mongodb.example.net --port 27017 –out /data/backup
```
-Khôi phục dữ liệu


Để khôi phục dữ liệu vừa backup ở trên ta dùng mongorestore
```sh
mongorestore –port <port number><path to

## Tham khảo

http://nodejs.vn/topic/17/t%E1%BB%95ng-quan-v%E1%BB%81-mongodb

http://nodejs.vn/topic/192/gi%E1%BB%9Bi-thi%E1%BB%87u-v%E1%BB%81-mongodb
