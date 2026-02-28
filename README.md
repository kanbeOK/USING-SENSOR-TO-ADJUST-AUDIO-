# USING-SENSOR-TO-ADJUST-AUDIO-

# 🛠 Linh kiện cần chuẩn bị

| Linh kiện | Công dụng |
| --- | --- |
| **Arduino Pro Micro** | Nhỏ gọn, dễ gắn lên găng tay và hỗ trợ cổng USB HID. |
| **MPU-6050** | Cảm biến 6 trục (Gia tốc + Con quay hồi chuyển). |
| **Điện trở nhiệt hoặc Flex Sensors** | Tự chế bằng giấy bạc và lõi bút chì (nếu muốn tiết kiệm và "lạ" hơn). |
| **Một chiếc găng tay cũ** | Loại găng tay len hoặc găng tay cơ khí mỏng. |





# CODE



$$\text{Angle} = \arctan2(A_y, A_z) \times \frac{180}{\pi}$$

```cpp
#include <Mouse.h>
#include <Wire.h>
// ... (Khai báo thư viện MPU6050)

void loop() {
  // Đọc dữ liệu từ MPU6050
  // Nếu nghiêng tay về phía trước > 30 độ
  if (pitch > 30) {
    Keyboard.press(KEY_MEDIA_VOLUME_UP); // Tăng âm lượng
    delay(100);
    Keyboard.releaseAll();
  }
}

```
