# iot-web (GitHub Pages)

Trang web mẫu kết nối **AWS IoT Core** qua **MQTT over WebSocket**.

## Thông tin đã cấu hình
- Region: `ap-southeast-1`
- IoT endpoint: `d06271991l2t0ukufb3u9-ats.iot.ap-southeast-1.amazonaws.com`
- Cognito Identity Pool ID: `ap-southeast-1:4b3cda65-f97c-4b12-9619-18ace38d8cf7`
- Topic publish: `web/control`
- Topic subscribe: `device/+/out`

## Cách dùng
1) Để chạy **online (GitHub Pages)**: chỉ cần push repo này. Trang sẽ tự thử tải SDK từ CDN nếu thiếu file cục bộ.
2) Để chạy **offline/local**: tải file SDK cho trình duyệt về thư mục `js/`:
   - Tải tại: https://unpkg.com/aws-iot-device-sdk/browser/aws-iot-sdk-browser-bundle.min.js
   - Lưu thành: `js/aws-iot-sdk-browser-bundle.min.js`

> Nếu không muốn phụ thuộc CDN trên GitHub Pages, bạn cũng có thể đưa file SDK vào `js/` rồi push lên repo.

## Kiểm tra
- Mở devtools (F12) → tab **Console**: cần thấy
  - `✅ Đã có AWS credentials từ Cognito.`
  - `🔗 MQTT connected as web-...`

## Ghi chú quyền
- Đảm bảo role **Cognito Unauth** có quyền: `iot:Connect`, `iot:Publish`, `iot:Subscribe`, `iot:Receive` trên các ARN/Topic tương ứng.
