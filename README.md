# MongoDB_setup
## 1. Giới thiệu
Đây là một cơ sở dữ liệu NoSQL thuộc loại cơ sở dữ liệu hướng văn bản mã nguồn mở, có hiệu năng, tính sẵn có và tính mở rộng cao được cung cấp và hổ trợ bởi 10gen.  MongoDB lưu trữ dữ liệu dạng BSON. Không giống như các cơ sở dữ liệu quan hệ lưu dữ cấu trúc dữ liệu theo các bảng, MongoDB lưu trữ cấu trúc dữ liệu thành văn bản dựa JSON với mô hình động (gọi là BSON) khiến cho việc tích hợp dữ liệu cho các ứng dụng trở nên dễ dàng và nhanh hơn.

Mục tiêu chính của Mongo là giữ lại các thuộc tính thân thiện của SQL. Do đó các câu truy vấn khá giống với SQL nên MongoDB khá thích hợp cho các lập trình viên đã quen với ngôn ngữ truy vấn SQL. MongoDB có một khối lượng tính năng lớn và hiệu năng cao. Với các loại dữ liệu phong phú, nhiều truy vấn và việc giảm thời gian phát triển trong việc mô hình hóa các đối tượng.
MongoDB được sử dụng tốt nhất với nhu cầu cần truy vấn động, cần tốc độ nhanh cho một cơ sở dữ liệu lớn vì MongoDB ngoài tốc độ đọc nhanh ra thì tốc độ ghi của nó rất nhanh.


## 2. Cài đặt

Để cài đặt phiên bản ổn định mới nhất của MongoDB:
```sh
$ sudo apt-get install -y mongodb-org
```
Để cài đặt một phiên bản MongoDB xác định, ví dụ 2.6.1
```sh
$ sudo apt-get install -y mongodb-org=2.6.1 mongodb-org-server=2.6.1 mongodb-org-shell=2.6.1 mongodb-org-mongos=2.6.1 mongodb-org-tools=2.6.1
```
## 3. Làm việc với MongoDB

###3.1 Chạy dịch vụ MongoDB

Trước khi chúng ta có thể tạo và lưu tài liệu trong cơ sở dữ liệu của mình, chúng ta phải chạy MongoDB. Sẽ không có bất cứ tài liệu nào được lưu nếu dịch vụ chưa được chạy.Chỉ một câu lệnh đơn giản để chạy mongodb:

```sh
$ sudo service mongod start
```

###3.2 Kết nối đến MongoDB

```sh
$ mongo 
```

## 4. Những lệnh phổ biến

### 4.1 Liệt kê tất cả cơ sở dữ liệu
```sh
$ show dbs;
```
### 4.2 Chọn một cơ sở dữ liệu
```sh
$ use db_name
```
### 4.3 Create
```sh
// Lưu một user
$ db.users.save({ name: 'Chris' });
// Lưu nhiều user 
$ db.users.save({ name: 'Chris'}, { name: 'Holly' });
```
### 4.4 Read
```sh
// show all users
$ db.users.find();

// Tìm một user xác định 
$ db.users.find({ name: 'Holly' });
```
### 4.5 Update
```sh
db.users.update({ name: 'Holly' }, { name: 'Holly Lloyd' });
```
### 4.6 Delete
```sh
// xóa tất cả 
db.users.remove({});
// Xóa một tài liệu

db.users.remove({ name: 'Holly' });
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
