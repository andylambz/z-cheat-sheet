# REDIS

## Install redis

```bash
docker run --name bnr-redis -p 6379:6379 -d redis
```

```bash
docker run --name bnr-redis \
  -p 6379:6379 \
  -v /opt/redis/data \
  -d redis redis-server --appendonly yes --requirepass “123456”
```

-v /opt/redis/data: Gắn một thư mục trên máy thật vào container để lưu trữ dữ liệu persistence.

--appendonly yes: Bật chế độ lưu dữ liệu liên tục (AOF).

--requirepass: Thiết lập mật khẩu truy cập.

## Open redis-cli

```bash
docker exec -it bnr-redis redis-cli
```

## ping
docker exec -it bnr-redis redis-cli ping

## View log
docker logs -f my-redis

***

redis-server --version

redis-cli --version

which redis-server

whereis redis

sudo find / -name "redis.conf"

***

Để làm quen với Redis, bạn có thể chia các câu lệnh thành các nhóm chức năng. Dưới đây là những lệnh cơ bản và hay dùng nhất mà bất kỳ ai mới bắt đầu cũng nên biết.

### 1. Nhóm lệnh Hệ thống (Kiểm tra kết nối)
Trước khi thao tác dữ liệu, bạn cần biết Redis có đang "nghe" mình không.

* `PING`: Trả về `PONG` nếu kết nối ổn định.
* `AUTH <password>`: Xác thực nếu Redis có đặt mật khẩu.
* `SELECT <index>`: Chuyển đổi giữa các database (mặc định có 16 DB, từ 0 đến 15).
* `FLUSHDB`: Xóa sạch dữ liệu của database hiện tại.

---

### 2. Thao tác với String (Key-Value đơn giản)
Đây là kiểu dữ liệu phổ biến nhất, dùng để lưu session, cache web...

* `SET <key> <value>`: Lưu một giá trị.
    * *Ví dụ:* `SET username "gemini"`
* `GET <key>`: Lấy giá trị của key.
* `DEL <key>`: Xóa một key.
* `EXISTS <key>`: Kiểm tra key có tồn tại không (trả về 1 nếu có, 0 nếu không).
* `INCR <key>`: Tăng giá trị của key lên 1 đơn vị (nếu là số).

---

### 3. Thao tác với Key (Quản lý vòng đời)
Dùng để quản lý thời gian tồn tại của dữ liệu.

* `EXPIRE <key> <seconds>`: Đặt thời gian sống cho key (hết thời gian sẽ tự xóa).
* `TTL <key>`: Kiểm tra xem key còn bao nhiêu giây thì "bay màu".
* `KEYS *`: Liệt kê tất cả các key đang có (Cẩn thận: đừng dùng lệnh này trên server thật có dữ liệu lớn vì nó gây treo Redis).
* `TYPE <key>`: Kiểm tra kiểu dữ liệu của key (string, list, set...).

---

### 4. Thao tác với List (Danh sách)
Dùng cho hàng đợi (queue) hoặc danh sách tin nhắn.

* `LPUSH <key> <value>`: Thêm phần tử vào **đầu** danh sách.
* `RPUSH <key> <value>`: Thêm phần tử vào **cuối** danh sách.
* `LPOP <key>`: Lấy và xóa phần tử ở **đầu** danh sách.
* `LRANGE <key> <start> <stop>`: Lấy một khoảng các phần tử.
    * *Ví dụ:* `LRANGE mylist 0 -1` (Lấy tất cả phần tử).



---

### 5. Thao tác với Hashes (Đối tượng)
Rất phù hợp để lưu trữ thông tin một đối tượng (ví dụ: thông tin User).

* `HSET <key> <field> <value>`: Thiết lập một thuộc tính của đối tượng.
    * *Ví dụ:* `HSET user:1 name "An" age 25`
* `HGET <key> <field>`: Lấy giá trị của một thuộc tính.
* `HGETALL <key>`: Lấy toàn bộ thuộc tính và giá trị của đối tượng đó.

---

### 6. Thao tác với Sets (Tập hợp không trùng lặp)
Dùng để lưu danh sách ID không trùng nhau, ví dụ danh sách người đã Like bài viết.

* `SADD <key> <member>`: Thêm phần tử vào tập hợp.
* `SMEMBERS <key>`: Lấy toàn bộ phần tử trong tập hợp.
* `SISMEMBER <key> <member>`: Kiểm tra một phần tử có nằm trong tập hợp không.

---

### Mẹo nhỏ cho bạn:
Nếu bạn đang dùng Docker, hãy vào giao diện gõ lệnh bằng cách:
`docker exec -it <tên_container> redis-cli`

**Bạn có muốn thử thực hành tạo một "User Profile" bằng lệnh Hash ngay bây giờ không?** Tôi có thể viết mẫu cho bạn.

***

INFO server	Xem phiên bản, ID tiến trình (PID), và thời gian uptime của server.
INFO clients	Xem có bao nhiêu ứng dụng đang kết nối vào Redis.
INFO memory	Xem Redis đang chiếm bao nhiêu RAM của hệ thống.

***

Cú pháp:

Bash
KEYS <pattern>
Các ví dụ phổ biến:

KEYS *: Lấy tất cả các key đang có trong DB.

KEYS user:*: Lấy tất cả các key bắt đầu bằng "user:".

KEYS *session*: Lấy các key có chứa chữ "session".

KEYS user:??: Lấy các key bắt đầu bằng "user:" và theo sau đúng 2 ký tự (dùng dấu ?).

***

Cú pháp:

Bash
SCAN <cursor> MATCH <pattern> COUNT <number>
Cách thực hiện trong redis-cli:

Bắt đầu với cursor là 0:
SCAN 0 MATCH user:* COUNT 100

Redis sẽ trả về một số cursor mới và một danh sách các key.

Bạn dùng số cursor mới đó để tiếp tục quét cho đến khi Redis trả về cursor số 0 (nghĩa là đã quét hết).

***

Xoá key theo pattern (an toàn)

Bash
redis-cli --scan --pattern "auth:token*" | xargs -L 1 redis-cli del
Giải thích:

--scan --pattern "auth:token*": Tìm các key bắt đầu bằng cụm đó một cách an toàn.

xargs -L 1 redis-cli del: Lấy từng kết quả tìm được và gửi lệnh xóa tới Redis.

***

Xoá key theo pattern (môi trường test)

2. Cách nhanh (Chỉ dùng cho môi trường Test/Dữ liệu ít)
Nếu số lượng key của bạn ít (vài nghìn key), bạn có thể dùng lệnh gộp này:

Bash
redis-cli del $(redis-cli keys "auth:token*")

***

Run với docker

3. Nếu bạn đang dùng Docker
Nếu Redis của bạn chạy trong Docker, hãy dùng lệnh sau để thực thi từ bên ngoài:

Bash
sudo docker exec -it bnr-redis sh -c "redis-cli --scan --pattern 'auth:token*' | xargs -L 1 redis-cli del"
