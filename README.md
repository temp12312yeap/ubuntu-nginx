기존의 image/ps 지우기
```
jun16017108@DESKTOP-HDDCTPS  ~  sudo docker stop $(sudo docker ps -a -q)
9bc21d2bdaf0
8e8e734d108d
 jun16017108@DESKTOP-HDDCTPS  ~  sudo docker rm $(sudo docker ps -a -q)
9bc21d2bdaf0
8e8e734d108d
 sudo docker rmi $(sudo docker images -q)
```
우분투 설치
```
sudo docker pull ubuntu
sudo docker pull ubuntu:22.04
```

우분투 생성 및 실행
```
 sudo docker run -it -d --name ubuntu-nginx3  fd1d8f58e8ae
 sudo docker exec -it ubuntu-nginx3 bash
```

apt update for nginx installation
```
 sudo docker exec -it ubuntu-nginx3 bash
root@d4753f53a68e:/# apt update
Get:1 http://archive.ubuntu.com/ubuntu jammy InRelease [270 kB]
Get:2 http://security.ubuntu.com/ubuntu jammy-security InRelease [110 kB]
Get:3 http://archive.ubuntu.com/ubuntu jammy-updates InRelease [119 kB]
Get:4 http://security.ubuntu.com/ubuntu jammy-security/restricted amd64 Packages [1784 kB]
Get:5 http://archive.ubuntu.com/ubuntu jammy-backports InRelease [109 kB]
Get:6 http://archive.ubuntu.com/ubuntu jammy/main amd64 Packages [1792 kB]
Get:7 http://security.ubuntu.com/ubuntu jammy-security/multiverse amd64 Packages [44.6 kB]
Get:8 http://security.ubuntu.com/ubuntu jammy-security/main amd64 Packages [1456 kB]
Get:9 http://security.ubuntu.com/ubuntu jammy-security/universe amd64 Packages [1069 kB]
Get:10 http://archive.ubuntu.com/ubuntu jammy/restricted amd64 Packages [164 kB]
Get:11 http://archive.ubuntu.com/ubuntu jammy/universe amd64 Packages [17.5 MB]
Get:12 http://archive.ubuntu.com/ubuntu jammy/multiverse amd64 Packages [266 kB]
Get:13 http://archive.ubuntu.com/ubuntu jammy-updates/multiverse amd64 Packages [50.4 kB]
Get:14 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 Packages [1734 kB]
Get:15 http://archive.ubuntu.com/ubuntu jammy-updates/universe amd64 Packages [1342 kB]
Get:16 http://archive.ubuntu.com/ubuntu jammy-updates/restricted amd64 Packages [1822 kB]
Get:17 http://archive.ubuntu.com/ubuntu jammy-backports/universe amd64 Packages [28.1 kB]
Get:18 http://archive.ubuntu.com/ubuntu jammy-backports/main amd64 Packages [50.4 kB]
Fetched 29.7 MB in 8s (3566 kB/s)
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
2 packages can be upgraded. Run 'apt list --upgradable' to see them.
```

nginx installation 
```
root@d4753f53a68e:/# apt install nginx
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following additional packages will be installed:
  fontconfig-config fonts-dejavu-core iproute2 libatm1 libbpf0 libbrotli1 libbsd0 libcap2-bin libdeflate0 libelf1
  libexpat1 libfontconfig1 libfreetype6 libgd3 libicu70 libjbig0 libjpeg-turbo8 libjpeg8 libmaxminddb0 libmd0 libmnl0
  libnginx-mod-http-geoip2 libnginx-mod-http-image-filter libnginx-mod-http-xslt-filter libnginx-mod-mail
  libnginx-mod-stream libnginx-mod-stream-geoip2 libpam-cap libpng16-16 libtiff5 libwebp7 libx11-6 libx11-data libxau6
  libxcb1 libxdmcp6 libxml2 libxpm4 libxslt1.1 libxtables12 nginx-common nginx-core ucf
Suggested packages:
  iproute2-doc libgd-tools mmdb-bin fcgiwrap nginx-doc ssl-cert
The following NEW packages will be installed:
  fontconfig-config fonts-dejavu-core iproute2 libatm1 libbpf0 libbrotli1 libbsd0 libcap2-bin libdeflate0 libelf1
  libexpat1 libfontconfig1 libfreetype6 libgd3 libicu70 libjbig0 libjpeg-turbo8 libjpeg8 libmaxminddb0 libmd0 libmnl0
  libnginx-mod-http-geoip2 libnginx-mod-http-image-filter libnginx-mod-http-xslt-filter libnginx-mod-mail
  libnginx-mod-stream libnginx-mod-stream-geoip2 libpam-cap libpng16-16 libtiff5 libwebp7 libx11-6 libx11-data libxau6
  libxcb1 libxdmcp6 libxml2 libxpm4 libxslt1.1 libxtables12 nginx nginx-common nginx-core ucf
0 upgraded, 44 newly installed, 0 to remove and 2 not upgraded.
Need to get 17.6 MB of archives.
After this operation, 56.4 MB of additional disk space will be used.
```

nginx 서비스 실행하기
```
root@d4753f53a68e:/# service nginx start
 * Starting nginx nginx                                                                                          [ OK ]
root@d4753f53a68e:/# service nginx status
 * nginx is running
```
