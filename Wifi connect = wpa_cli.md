Để kết nối WiFi sử dụng wpa_cli trên Linux, bạn có thể thực hiện theo các bước sau:

Cài đặt wpa_supplicant:
Nếu bạn chưa có wpa_supplicant cài đặt, bạn có thể cài đặt nó bằng lệnh:
sudo apt-get install wpasupplicant

Cấu hình wpa_supplicant:

Tạo hoặc chỉnh sửa file cấu hình /etc/wpa_supplicant/wpa_supplicant.conf để thêm thông tin mạng WiFi của bạn.
```bash
sudo nano /etc/wpa_supplicant/wpa_supplicant.conf
```


Thêm vào file cấu hình này thông tin mạng WiFi:
```bash
network={
    ssid="Tên_WiFi"
    psk="Mật_khẩu_WiFi"
}
```
Sử dụng wpa_cli để kết nối:

Bạn có thể sử dụng wpa_cli để quét và kết nối tới mạng WiFi. Dưới đây là các lệnh cơ bản:

Mở wpa_cli:
```bash
sudo wpa_cli
```
Quét mạng WiFi xung quanh:
```bash
scan
```
Xem kết quả quét:
```bash
scan_results
```
Thêm mạng WiFi:
```bash
add_network
```
Chỉnh sửa thông tin mạng:
```bash
set_network 0 ssid "\"Tên_WiFi\""
set_network 0 psk "\"Mật_khẩu_WiFi\""
```
Kích hoạt mạng:
```bash
enable_network 0
```
Lưu cấu hình:
```bash
save_config
```
Kết nối mạng:
```bash
select_network 0
```
Kiểm tra kết nối:
Sau khi thực hiện các lệnh trên, bạn có thể kiểm tra trạng thái kết nối WiFi bằng lệnh:
```bash
sudo wpa_cli status
```
# 1. Mở wpa_cli
```bash
sudo wpa_cli
```
# 2. Quét mạng WiFi xung quanh
```bash
scan
```
# 3. Xem kết quả quét
```bash
scan_results
```
# 4. Thêm mạng WiFi
```bash
add_network
```
# Lệnh này sẽ trả về một ID mạng (thường là 0 nếu bạn chưa thêm mạng nào trước đó).

# 5. Cấu hình mạng WiFi
```bash
set_network <network_id> ssid "\"Tên_WiFi\""
set_network <network_id> psk "\"Mật_khẩu_WiFi\""
```
# 6. Kích hoạt mạng
```bash
enable_network <network_id>
```
# 7. Chọn mạng để kết nối
```bash
select_network <network_id>
```
# 8. Lưu cấu hình
```bash
save_config
```

# 9. Xóa mạng
```bash
remove_network <network_id>
```
# 10. Hủy kích hoạt mạng
```bash
disable_network <network_id>
```
# 11. Kiểm tra trạng thái kết nối
```bash
status
```
# 12. Xem danh sách các mạng đã thêm
```bash
list_networks
```
# 13. Ngắt kết nối khỏi mạng hiện tại
```bash
disconnect
```
# 14. Kết nối lại mạng
```bash
reconnect
```
# 15. Khởi động lại wpa_supplicant
```bash
reconfigure
```
```bash
# Ví dụ cụ thể:
# Giả sử bạn muốn kết nối đến mạng WiFi có SSID là "MyWiFi" và mật khẩu là "password123".

# 1. Mở `wpa_cli`
sudo wpa_cli

# 2. Quét mạng WiFi
scan

# 3. Xem kết quả quét
scan_results

# 4. Thêm mạng mới
add_network
# Giả sử ID mạng trả về là `0`.

# 5. Cấu hình mạng
set_network 0 ssid "\"MyWiFi\""
set_network 0 psk "\"password123\""

# 6. Kích hoạt mạng
enable_network 0

# 7. Chọn mạng để kết nối
select_network 0

# 8. Lưu cấu hình
save_config

# 9. Kiểm tra trạng thái kết nối
status

sudo systemctl restart wpa_supplicant
```bash

