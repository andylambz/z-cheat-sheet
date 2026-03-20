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

