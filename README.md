# Bai 2: Khoi chay Nginx voi Port Mapping

Ngay chay: 2026-10-12 09:35

## Lenh: docker run -d -p 8080:80 --name my-web nginx:alpine

```text
365a23808fc912c09df2c7d9c791c9ce5e9fb52786afa4921c11126686e9c7a7
```

## Lenh: docker ps

```text
CONTAINER ID   IMAGE          COMMAND                  CREATED         STATUS                  PORTS                                     NAMES
365a23808fc9   nginx:alpine   "/docker-entrypoint.ΓÇª"   2 seconds ago   Up Less than a second   0.0.0.0:8080->80/tcp, [::]:8080->80/tcp   my-web
```

## Lenh: curl.exe http://localhost:8080

```text
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed

  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0
100   896  100   896    0     0  10833      0 --:--:-- --:--:-- --:--:-- 10926
100   896  100   896    0     0  10728      0 --:--:-- --:--:-- --:--:-- 10795
<!DOCTYPE html>
<html>
<head>
<title>Welcome to nginx!</title>
<style>
html { color-scheme: light dark; }
body { width: 35em; margin: 0 auto;
font-family: Tahoma, Verdana, Arial, sans-serif; }
</style>
</head>
<body>
<h1>Welcome to nginx!</h1>
<p>If you see this page, nginx is successfully installed and working.
Further configuration is required for the web server, reverse proxy, 
API gateway, load balancer, content cache, or other features.</p>

<p>For online documentation and support please refer to
<a href="https://nginx.org/">nginx.org</a>.<br/>
To engage with the community please visit
<a href="https://community.nginx.org/">community.nginx.org</a>.<br/>
For enterprise grade support, professional services, additional 
security features and capabilities please refer to
<a href="https://f5.com/nginx">f5.com/nginx</a>.</p>

<p><em>Thank you for using nginx.</em></p>
</body>
</html>
```

## Lenh: docker stop my-web

```text
my-web
```

## Lenh: docker rm my-web

```text
my-web
```

## Lenh: docker ps -a --filter name=my-web

```text
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
```
## Giải thích

- `-d`: chạy container ở chế độ nền.
- `-p 8080:80`: ánh xạ cổng 8080 của máy tính vào cổng 80 trong container Nginx.
- `--name my-web`: đặt tên container là `my-web`.
- `nginx:alpine`: image Nginx nhẹ, dựa trên Alpine Linux.
- `docker stop` rồi `docker rm`: dừng và xóa container sau khi thử nghiệm.

## Kết quả

- Lệnh `curl` trả về trang HTML có dòng "Welcome to nginx!", chứng tỏ Web Server hoạt động.
- Sau khi dọn dẹp, không còn container `my-web` trong danh sách.