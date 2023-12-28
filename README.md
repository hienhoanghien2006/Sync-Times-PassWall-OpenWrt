# TỰ ĐỘNG CẬP NHẬT THỜI GIAN CHO ROUTER SỬ DỤNG VPN PASSWALL, ShadowSocksR Plus+, V2RAY,...
Đồng bộ hóa ngày openwrt bằng cách chọn ngày từ miền đã chọn.

Đồng bộ hóa thời gian trong OpenWrt bằng cách lấy dữ liệu thời gian từ miền đã chọn.

Hỗ trợ đồng bộ thời gian khi có kết nối modem/internet.

Trình kiểm tra kết nối (nếu sử dụng chế độ cron, tập lệnh sẽ kiểm tra kết nối, sau đó khởi động lại ứng dụng VPN nếu không có kết nối internet)

Cài đặt múi giờ tự động tuân theo LuCI - System - System - Timezone.

Hỗ trợ cài đặt múi giờ cho VPN:

OpenClash

Passwall

ShadowsocksR

ShadowsocksR++

v2ray

v2rayA

xray

Libernet

Xderm Mini

Wegare STL

Sử dụng mặc định - Sử dụng cơ bản

Cài đặt các gói yêu cầu trước bằng cách mở terminal:
```

opkg update && opkg install curl wget
```

Dán lệnh bên dưới để cài đặt tập lệnh times-openwrt

Dùng wget:
```
wget --no-check-certificate "https://raw.githubusercontent.com/hienhoanghien2006/auto-times-passwall-openwrt/main/autotime-openwrt" -O /usr/bin/autotime-openwrt && chmod +x /usr/bin/autotime-openwrt
```

dùng curl:
```

curl -sL https://raw.githubusercontent.com/hienhoanghien2006/auto-times-passwall-openwrt/main/autotime-openwrt > /usr/bin/autotime-openwrt && chmod +x /usr/bin/autotime-openwrt
```

Nhập lệnh bên dưới vào LuCI -> System -> Startup -> Local Startup hoặc tại rc.local nếu ở trong terminal

Ví dụ dùng mạng Viettel:
```

/usr/bin/times-openwrt m.tv360.vn
```

Nếu sử dụng crontab (kiểm tra kết nối cứ sau 1 giờ, sau đó khởi động lại vpn nếu không có kết nối), sao chép lệnh bên dưới vào LuCI -> System -> Schedule Tasks Ví dụ:
```

0 * * * * /usr/bin/times-openwrt m.tv360.vn cron
```

Lệnh trên cũng có thể được bao gồm trong tệp/etc/crontabs/root

Đối với các tùy chỉnh thời gian định kỳ khác, hãy xem crontab.guru

Để update tập lệnh hãy thực hiện lệnh bên dưới:
```

/usr/bin/autotime-openwrt update
```
Cập nhật thành công ta được đoạn code như sau:

```
autotime-openwrt: Update tệp lệnh...
autotime-openwrt: Đang tải tệp lệnh...
Downloading 'https://raw.githubusercontent.com/hienhoanghien2006/auto-times-passwall-openwrt/main/autotime-openwrt'
Connecting to 185.199.109.133:443
Writing to '/root/jamup.sh'
/root/jamup.sh       100% |*******************************|  7200   0:00:00 ETA
Download completed (7200 bytes)
autotime-openwrt: update thành công.
autotime-openwrt: Đã xóa tệp update!
Cách dùng: Thêm tên miền sau tệp lệnh!.
autotime-openwrt: Thiếu tên miền/URL!. Để biết thêm chi tiết vào Zalo: https://zalo.me/hoanghien14 FB Hoàng Minh Hiển.
```
# Mọi thắc mắc vui lòng liên hệ zalo Hoàng Minh Hiển: 
#       http://zalo.me/hoanghien14

Đội ngũ phát triển
Tập lệnh và codes của AlkhaNet by Teguh Surya Mungaran và được tùy biến lại bởi Hoàng Minh Hiển

Mã GMT và các mã khác của Vito H.S

Trình kiểm tra và cài đặt opkg, kiểm tra internet, vpn manager, codes chọn GMT của Helmi Amirudin
    

