# 🚗 ESP32 BLE Navigation Display (Sygic to OLED)

Hiển thị hướng dẫn chỉ đường thời gian thực từ ứng dụng Sygic (hoặc app trung gian) đến màn hình OLED 1.3 inch thông qua kết nối BLE với ESP32.

## 🧰 Phần cứng sử dụng

| Thiết bị             | Mô tả                                      |
|----------------------|---------------------------------------------|
| ESP32 DevKit V1      | Vi điều khiển chính, hỗ trợ BLE            |
| OLED SSD1306 (1.3")  | Màn hình OLED I2C, độ phân giải 128x64     |
| Điện thoại Android   | Chạy ứng dụng Sygic + app gửi BLE (giả lập) |

## 🔌 Sơ đồ kết nối

| OLED SSD1306 | ESP32 GPIO |
|--------------|------------|
| VCC          | 3.3V       |
| GND          | GND        |
| SCL          | GPIO 22    |
| SDA          | GPIO 21    |

## 💡 Chức năng

- Nhận dữ liệu BLE từ điện thoại theo định dạng: `LEFT:200m`, `RIGHT:100m`, `STRAIGHT:50m`
- Hiển thị hướng rẽ và khoảng cách trên OLED
- Thiết kế đơn giản, dễ mở rộng thêm buzzer, rung, icon rẽ,...

## 📲 Ứng dụng điện thoại

Dữ liệu được gửi từ điện thoại qua BLE (app tự viết hoặc test bằng nRF Connect).  
Ví dụ: Gửi chuỗi `"LEFT:150m"` sẽ hiển thị:

Turn: LEFT
Dist: 150m


> ⚠️ *Sygic không hỗ trợ xuất BLE trực tiếp, cần app trung gian hoặc SDK riêng của Sygic.*

## 🔧 Thư viện sử dụng

- [Adafruit_SSD1306](https://github.com/adafruit/Adafruit_SSD1306)
- [Adafruit_GFX](https://github.com/adafruit/Adafruit-GFX-Library)
- `BLEDevice` từ ESP32 core

Cài bằng Library Manager trong Arduino IDE hoặc PlatformIO.

## 📸 Hình ảnh minh họa

*(Thêm ảnh dự án tại đây nếu có)*

## 🧪 Hướng dẫn sử dụng

1. Nạp mã vào ESP32
2. Kết nối điện thoại với ESP32 qua BLE (tên thiết bị: `ESP32_Navi`)
3. Gửi chuỗi điều hướng qua BLE để hiển thị trên OLED

## 📦 Mở rộng

- Thêm biểu tượng rẽ (icon bitmap)
- Tích hợp với Sygic SDK hoặc Google Maps API
- Buzzer cảnh báo khi sắp đến ngã rẽ
- Giao diện UX đẹp hơn

## 🧑‍💻 Tác giả

- Tên: Nguyễn Văn Tùng

---

**ESP32 BLE Navigation - Made for Embedded Navigation UI**
