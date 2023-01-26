# Cài đặt GNS3 
## Môi trường
Máy ảo Ubuntu server 18.04 (hyper-v)
IP 192.168.1.12

Reference: https://docs.gns3.com/docs/getting-started/installation/linux
Ở lệnh 
```
sudo add-apt-repository ppa:gns3/ppa
```
Nếu bị stuck thì edit file: 
```
sudo nano /etc/gai.conf
```
Bỏ comment (#), và đổi từ 10 thành 100 ở dòng:
```
precedence ::ffff:0:0/96  100
```
