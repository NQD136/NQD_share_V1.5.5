# 🤖 Zalo ChatBot

**Zalo ChatBot** được phát triển bằng **JavaScript** với thư viện **zlbotdqt**.  
Tác giả: **SBT** – [GitHub](https://github.com/itisme)
Mod lại bởi **NQD** – [GitHub](https://github.com/NQD136)

```
                  .----.
      .---------. | == |
      |.-"""""-.| |----|
      ||       || | == |
      ||       || |----|
      |'-.....-'| |::::|
      `"")---(""` |___.|
     /:::::::::::\" _  "
    /:::=======:::\`\`\
    `"""""""""""""`  '-'
```

---

## 📌 Tính năng (v1.5.5)

### 🛠 Quản lý nhóm Zalo tự động
- Tự động bảo vệ nhóm
  - **Chống Spam**
  - **Chặn Liên kết**
  - **Lọc Từ Ngữ Xấu**
  - **Chặn Nội Dung Tiêu Cực**
  - **Chống Gửi Ảnh Nhạy Cảm**
  - **Chống Thu Hồi Tin Nhắn**
  - **Chỉ Được Phép Gửi Tin Nhắn Văn Bản**
  - **Kick Thành Viên**
  - **Chặn Thành Viên**
  - **Tự Động Duyệt Thành Viên**
  - **Tin Nhắn Tag All**

### 🎯 Social Bot
- Hơn **50 lệnh** giải trí:
  - 📺 YouTube
  - 🎵 TikTok
  - 🎶 ZingMP3, NhacCuaTui
  - ...và nhiều hơn nữa.

### 🎮 Tiện ích game

- **Tài xỉu**
- **Chẵn lẻ**
- **Bầu cua**
- **Kéo búa bao**
- **Nông trại**
---

## 🚀 Hướng dẫn sử dụng

**Yêu Cầu Bắt Buộc: Có Bản Nodejs V20.9.0**

### 1️⃣ Cấu hình
Mở tệp `config.json` trong thư mục `assets` và thiết lập:

- **Cookie**, **Imei**
 - Sử dụng tiện ích get-imei-cookie [tại đây](https://www.mediafire.com/file/u65t0y95nw0oujy/get-imei-cookie-js.zip/file)

 - Giải nén file ra sau đó đưa lên tiện ích chrome để sử dụng

- **UserAgent**  
  - Giữ mặc định hoặc lấy UserAgent mới tại [whatmyuseragent.com](https://whatmyuseragent.com/)

---

### 2️⃣ Chạy Bot
Chạy file:
```bash
run.bat
```

---

### 3️⃣ Thiết lập quyền Admin
- Lấy **UID** tài khoản cần cấp quyền qua terminal.
- Thêm vào file:
```
assets/data/list_admin.json
```

---

### 4️⃣ Khởi động lại bot
Sau khi cấu hình, hãy **khởi động lại** bot để áp dụng thay đổi.

---
---


## Hướng dẫn khởi chạy trên termux(Android)
**Lưu ý**: Khi chạy trên termux cần thay lại code file **bot.js**, lấy file code đã sửa [tại đây](https://www.mediafire.com/file/aadre72xnkd1r76/bot.js/file)

**B1: tải root debian**
```
pkg update && pkg upgrade -y
pkg install proot-distro -y
proot-distro install debian
proot-distro login debian
```

**Sau khi hiện root@localhost** thì vào B2

**B2: tải node phù hợp**
```
apt-get update

apt-get install -y curl python3 make g++ gcc

curl -L https://raw.githubusercontent.com/tj/n/master/bin/n -o n

bash n 20.10.0

export PATH="/usr/local/bin:$PATH"

if [ -f /root/.bashrc ]; then
    grep -qxF 'export PATH="/usr/local/bin:$PATH"' /root/.bashrc || echo 'export PATH="/usr/local/bin:$PATH"' >> /root/.bashrc

fi
```
echo "Phiên bản NodeJS:"
```
node -v
```
echo "Phiên bản npm:"
```
npm -v
```

**B3: git clone file bot**
```
apt install git ffmpeg  -y

git clone https://github.com/NQD136/NQD_share_V1.5.5.git

cd NQD_share_V1.5.5
```

**B4: build canvas**
```
apt update && apt install -y \
  build-essential \
  libcairo2-dev \
  libpango1.0-dev \
  libjpeg-dev \
  libgif-dev \
  librsvg2-dev \
  pkg-config
npm install canvas
npm install dotenv
```

**B5 tải mariaDB**
```
apt update && apt upgrade -y
apt install mariadb-server mariadb-client -y
```

**Khởi động sql**
```
service mariadb start
```
*Đặt mật khẩu và enter*

**B6: thêm sql vào bashrc**
```
nano ~/.bashrc

```
**thêm Auto start MariaDB khi vào Debian**
```
if ! pgrep -x mysqld > /dev/null; then
    service mariadb start
fi
```
**vào cuối file và thoát rồi chạy**
```
source ~/.bashrc
```

**B7 tạo .env**
```
nano .env
```
**Dán**
```
DB_HOST=127.0.0.1
DB_PORT=3300
DB_USER=root
DB_PASSWORD=123
DB_NAME=nqd_db
```

**LƯU Ý**: Nếu DB_PASSWORD có đặt thì cần vô file **database-config.json** ở **nano /root/NQD_share_V1.5.5/assets/json-data/database-config.json**

**Sẽ thấy**
```
{
  "nameServer": "N Q D",
  "host": "localhost",
  "user": "root",
  "password": "123",
  "database": "bot-zalo-dqt",
  "port": 3300,
  "tablePlayerZalo": "players_zalo",
  "tableAccount": "account",
  "dailyReward": 100000000000
}
```
**"password": "123"** dòng này mk phải để đúng với **DB_PASSWORD**, nếu không sẽ kông sử dụng được các tác vụ game

**B8: build lại node_modules**
```
rm -rf node_modules package-lock.json && npm i
```

## ❤️ Lời cảm ơn

**N Q D** chúc bạn sử dụng bot vui vẻ

Cảm ơn bạn đã sử dụng mã nguồn của tôi.  
Hy vọng bạn sẽ thích những tính năng mà **Zalo ChatBot** mang lại!
**Tham gia group của tôi**[tại đây](https://zalo.me/g/ffqiqj984)
**Liên hệ với N Q D**[tại đây](https://zaloapp.com/qr/p/gocjf95sb529?src=qr)
