# mongodb

### Install mongodb

```bash
docker run -d \
  --name mongodb-shared \
  --restart always \
  -p 27018:27017 \
  -v /opt/mongo-data:/data/db \
  mongo:4.0
```

docker run: Lệnh cơ bản của Docker dùng để khởi tạo và chạy một container mới.

-d (detach): Chạy container ở chế độ ngầm (background). Lệnh sẽ trả lại Terminal cho người dùng ngay sau khi thực thi thành công thay vì bị treo ở màn hình log.

--name mongodb-shared: Định danh tên cho container là mongodb-shared.

--restart always: Cấu hình tự động khởi động. Biến container này hoạt động giống như một System Service thực thụ: tự động chạy lại nếu tiến trình bị lỗi (crash) hoặc khi máy chủ vật lý khởi động lại (reboot).

-p 27018:27017 (Port Mapping): Ánh xạ cổng mạng theo quy tắc [Cổng_Server_Vật_Lý]:[Cổng_Container].

Mở cổng 27018 trên Server vật lý và kết nối nó thẳng vào cổng 27017 (cổng mặc định của MongoDB) nằm bên trong container.

-v /opt/mongo-data:/data/db (Volume Mount): Thiết lập lưu trữ dữ liệu bền vững (Persistent Storage) theo quy tắc [Thư_mục_Server_Vật_Lý]:[Thư_mục_Container].

Gắn thư mục /opt/mongo-data trên máy chủ vật lý vào thư mục chứa dữ liệu mặc định của Mongo là /data/db.

mongo:4.0: Tên và phiên bản (tag) của Docker Image.


### Check info, start, stop, restart

```bash
docker ps

docker ps -a

docker stop mongodb-shared

docker start mongodb-shared

docker restart mongodb-shared
```

### Open terminal mongo

```bash
docker exec -it mongodb-shared mongo
```

docker exec: Lệnh yêu cầu Docker thực thi một tiến trình mới bên trong một container đang hoạt động.

-it: Là sự kết hợp của -i (Interactive: giữ cho luồng nhập dữ liệu mở) và -t (TTY: cấp phát một giao diện màn hình ảo). Hiểu đơn giản, nó cho phép bạn gõ phím và xem kết quả tương tác trực tiếp hệt như đang dùng Terminal của máy tính đó.

mongodb-shared: Tên của container mà bạn muốn can thiệp vào.

### Open terminal mongo and login

```bash
docker exec -it mongodb-shared mongo -u <username> -p

docker exec -it mongodb-shared mongo my_db
```

### Exit

```bash
exit
```

## Mongodb danh sách câu lệnh cơ bản

### Database

```bash
show dbs
use my_database
db
db.dropDatabase()
```

### Collection

```bash
show collections
db.createCollection("users")
db.users.drop()
```

### Document

```bash
db.users.insertOne({ name: "Nguyễn Văn A", age: 25, email: "a@gmail.com" })
db.users.insertMany([
    { name: "Trần Thị B", age: 22 },
    { name: "Lê Văn C", age: 30 }
])

db.users.find()
db.users.find().pretty()
db.users.find({ age: 25 })
db.users.findOne({ name: "Nguyễn Văn A" })

db.users.updateOne(
    { name: "Nguyễn Văn A" }, 
    { $set: { age: 26 } }
)
db.users.updateMany(
    { age: 22 }, 
    { $set: { status: "active" } }
)

db.users.deleteOne({ name: "Nguyễn Văn A" })
db.users.deleteMany({ status: "inactive" })
db.users.deleteMany({})
```

