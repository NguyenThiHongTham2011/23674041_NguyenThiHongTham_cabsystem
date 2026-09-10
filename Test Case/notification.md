# Test Cases - Notification API

## Scenario 1: Gửi thông báo

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC_NOTIFICATION_001 | Gửi thông báo | Gửi thông báo hợp lệ | Hệ thống thông báo đang hoạt động | 1. Gửi POST `/notifications` | Người nhận hợp lệ, nội dung hợp lệ | API trả về `201`, thông báo được tạo thành công | High |
| TC_NOTIFICATION_002 | Gửi thông báo | Gửi thông báo đến đúng khách hàng | Khách hàng tồn tại | 1. Gửi POST `/notifications` | Customer ID hợp lệ, nội dung thông báo | Thông báo được gửi đến đúng khách hàng | High |
| TC_NOTIFICATION_003 | Gửi thông báo | Gửi thông báo đến đúng tài xế | Tài xế tồn tại | 1. Gửi POST `/notifications` | Driver ID hợp lệ, nội dung thông báo | Thông báo được gửi đến đúng tài xế | High |
| TC_NOTIFICATION_004 | Gửi thông báo | Gửi thông báo với thông tin không hợp lệ | API hoạt động bình thường | 1. Gửi POST `/notifications` với dữ liệu không hợp lệ | Người nhận hoặc nội dung không hợp lệ | Hệ thống không tạo thông báo sai dữ liệu | Medium |

## Scenario 2: Thông báo không tìm được tài xế

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC_NOTIFICATION_005 | Thông báo không tìm được tài xế | Gửi thông báo khi không có tài xế phù hợp | Booking đã được tạo nhưng không tìm được tài xế | 1. Gửi POST `/notifications/no-driver` | Booking hợp lệ | API trả về `200`, khách hàng nhận được thông báo không tìm được tài xế | High |
| TC_NOTIFICATION_006 | Thông báo không tìm được tài xế | Gửi thông báo cho booking không tồn tại | Booking không tồn tại | 1. Gửi POST `/notifications/no-driver` | Booking ID không tồn tại | Hệ thống không gửi thông báo sai booking | Medium |
| TC_NOTIFICATION_007 | Thông báo không tìm được tài xế | Kiểm tra nội dung thông báo | Không tìm được tài xế | 1. Gửi yêu cầu thông báo 2. Kiểm tra thông báo nhận được | Booking hợp lệ | Thông báo thể hiện rõ việc không tìm được tài xế | Medium |
