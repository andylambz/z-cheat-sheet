# INSTALL REDIS SERVER

redis-server --version

redis-cli --version

which redis-server

whereis redis

sudo find / -name "redis.conf"


INSTALL

docker run --name bnr-redis -p 6379:6379 -d redis


docker run --name bnr-redis \
  -p 6379:6379 \
  -v /opt/redis/data \
  -d redis redis-server --appendonly yes --requirepass “123456”



-v /my/local/path:/data: Gắn một thư mục trên máy thật vào container để lưu trữ dữ liệu persistence.

--appendonly yes: Bật chế độ lưu dữ liệu liên tục (AOF).

--requirepass: Thiết lập mật khẩu truy cập.
