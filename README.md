Hassio for OrangePi PC
Cài đặt ARMBIAN version Armbian_22.05.4_Orangepipc_bullseye_current_5.15.48
Set tài khoản admin pass: Theo ý bạn
--------------------------------
Đăng nhập admin
----------------
Bước1: Cập nhật OS:
sudo apt-get update
sudo apt-get upgrade
----------------
Bước 2: Cài đặt Python3:
sudo apt-get install python3 python3-dev
sudo apt-get install python3-venv python3-pip
python3 -V
Bước 3: Cài bổ trợ
sudo apt-get install \
jq \
wget \
curl \
apparmor-utils \
udisks2 \
libglib2.0-bin \
network-manager \
dbus -y
------
Hoặc:
sudo apt-get install jq curl avahi-daemon apparmor-utils udisks2 libglib2.0-bin network-manager dbus wget -y
----------------
Bước 4: Cài đặt Docker Engine
sudo curl -fsSL get.docker.com | sh
----------------
Bước 5: Cài đặt the OS Agent theo đúng cấu trúc Orange PI PC là armv7
---
wget https://github.com/home-assistant/os-agent/releases/download/1.2.2/os-agent_1.2.2_linux_armv7.deb
sudo dpkg -i os-agent_1.2.2_linux_armv7.deb
---
Sau khi cài đặt xong, bạn dùng lệnh dưới để test:
gdbus introspect --system --dest io.hass.os --object-path /io/hass/os
----------------
Bước 6: Cài đặt Home Assisistant Supervised Debian Package
Lần lượt gõ lệnh sau:
wget https://github.com/home-assistant/supervised-installer/releases/latest/download/homeassistant-supervised.deb 
sudo dpkg -i homeassistant-supervised.deb
----------------
Lệnh theo dõi trạng thái:
journalctl -f

Đợi một lúc để HassIO cài đặt, sau đó vào  http://diachiIP:8123/  ví dụ http://192.168.0.110:8123 để cài đặt trang điều khiển của Hass IO xem chi tiết bước đó tại đây.
