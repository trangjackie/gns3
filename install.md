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

## Running KVM Nested in Microsoft Hyper-V 
Mặc định máy ảo không hỗ trợ VM extension do đó không chạy KVM được. Để enable KVM cần thực hiện:
- Download this PowerShell script from Github (written by Microsoft) --> file Enable-NestedVm.ps1
- Copy the script to your desktop
- Open up an elevated PowerShell instance
- Change current folder to the location of the PowerShell Script
- Run the following command to allow for script execution in Powershell
```
Set-ExecutionPolicy Bypass
```
- Run .\nameofscript.ps1 name-of-linux-vm-in-hyper-v
- If all goes well it should prompt you asking if you want to expose Virtualization Extensions. Answer Yes, also enable any other additions as you wish.
- After the script completes, boot the VM in Hyper-V and you should now have access to the virtualization extensions required for KVM/XEN.

