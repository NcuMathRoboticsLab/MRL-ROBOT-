# MRL ROBOT 樹梅派作業系統燒入

# 簡介

NCU MRL 之 Turtlebot3 與 Minibot 通用樹梅派作業系統映像檔，以 [Ubuntu server 20.04](http://cdimage.ubuntu.com/ubuntu-server/focal/daily-preinstalled/current/) 製作而成

此映像檔是使用 16G 大小之 SD card 製作成，因此僅支援 16G 以上之 SD card

預設之使用者名稱與密碼為以下：

**使用者名稱：** pi

**密碼：** mrlrobot

**root 密碼：** mrlrobot

# OS 映像檔下載

[**MRL-ROBOT-v2.img.gz**](https://drive.google.com/file/d/1Juw80gOXfAmqQGVdiwhU69F1KMXzhPBM/view) 

[**MRL-ROBOT-v2.img.xz**](https://drive.google.com/file/d/1t6OtquqjAhgaKC-g_HZmwYWBKy52GM1q/view) 

# 使用 Raspberry Pi Imager 、 Rufus 或 Disks Utility 燒入

### [Rufus](https://rufus.ie/)

![](https://i.imgur.com/beAcTJG.png)

### [Raspberry Pi Imager](https://www.raspberrypi.org/software/)

![](https://emanual.robotis.com/assets/images/platform/turtlebot3/setup/rpi_imager.gif)

### Disks Utility

![](https://emanual.robotis.com/assets/images/platform/turtlebot3/setup/disks.gif)

#  調整分區大小

由於此映像檔是使用 16G 大小之 SD card 製作成，如果是使用 16G 以上記憶卡需調整分區大小

下圖為使用 [Gparted](https://gparted.org/) 之示意圖

![](https://emanual.robotis.com/assets/images/platform/turtlebot3/setup/gparted.gif)

# 根據 Turtlebot 或 Minibot 選擇要使用之 catkin_ws

### Turtlebot

```bash=
# 更改家目錄底下之 turtlebot_ws 名稱成 catkin_ws 並移除 minibot_ws
mv /home/pi/turtlebot_ws /home/pi/catkin_ws && rm -r /home/pi/minibot_ws
```

### Minibot

```bash=
# 更改家目錄底下之 minibot_ws 名稱成 catkin_ws 並移除 turtlebot_ws
mv /home/pi/minibot_ws /home/pi/catkin_ws && rm -r /home/pi/turtlebot_ws
```

# 修改網路設定
此映像檔支援 Network Manager，可以使用 nmtui 進行網路設定

```bash=
nmtui
```

### Ethernet

**預設為 10.0.0.1/24**

![](https://i.imgur.com/6Cbo0hL.png)

### WIFI

![](https://i.imgur.com/ivxVTpt.png)


# 更改密碼

```bash=
passwd
```

# 更改使用者名稱

假設要將用戶 'peter' 更改為 'paul'

```bash=
# 需使用 root 登入
groupadd paul
usermod -d /home/paul -m -g paul -l paul peter
```

# 更改主機名稱(hostname)

```bash=
sudo vim /etc/hostname
```
