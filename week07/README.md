# 7주차

- 도커 컴포즈


docker compose ps
NAME                IMAGE            COMMAND                  SERVICE   CREATED          STATUS                    PORTS
guestbook-nginx-1   nginx:alpine     "/docker-entrypoint.…"   nginx     54 seconds ago   Up 40 seconds             0.0.0.0:8080->80/tcp, [::]:8080->80/tcp
guestbook-redis-1   redis:7-alpine   "docker-entrypoint.s…"   redis     54 seconds ago   Up 54 seconds (healthy)   6379/tcp
guestbook-web-1     guestbook-web    "python app.py"          web       54 seconds ago   Up 48 seconds (healthy)   5000/tcp


docker compose down && docker compose up -d
[+] down 4/4
 ✔ Container guestbook-nginx-1 Removed                                                                               0.0s
 ✔ Container guestbook-web-1   Removed                                                                               0.0s
 ✔ Container guestbook-redis-1 Removed                                                                               0.0s
 ✔ Network guestbook_default   Removed                                                                               0.2s
[+] up 4/4
 ✔ Network guestbook_default   Created                                                                               0.0s
 ✔ Container guestbook-redis-1 Healthy                                                                               6.0s
 ✔ Container guestbook-web-1   Healthy                                                                              11.6s
 ✔ Container guestbook-nginx-1 Started 

docker compose down -v && docker compose up -d
[+] down 5/5
 ✔ Container guestbook-nginx-1 Removed                                                                               0.4s
 ✔ Container guestbook-web-1   Removed                                                                               3.2s
 ✔ Container guestbook-redis-1 Removed                                                                               0.2s
 ✔ Volume guestbook_redis-data Removed                                                                               0.0s
 ✔ Network guestbook_default   Removed                                                                               0.2s
[+] up 5/5
 ✔ Network guestbook_default   Created                                                                               0.0s
 ✔ Volume guestbook_redis-data Created                                                                               0.0s
 ✔ Container guestbook-redis-1 Healthy                                                                               5.9s
 ✔ Container guestbook-web-1   Healthy                                                                              11.5s
 ✔ Container guestbook-nginx-1 Started 

.env 는 비밀번호 정보를 포함한 민감정보가 포함되어 있어 
이를 깃허브에 올릴 시 민감정보 유출이 발생하기 때문에 ignore로 막습니다
