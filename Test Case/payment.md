# Test Cases - Payment API

## Scenario 1: Tính cước và thanh toán

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC_PAYMENT_001 | Tính cước và thanh toán | Tính cước cho chuyến hợp lệ | Chuyến đã hoàn thành | 1. Gửi GET `/trips/{tripId}/fare` | tripId = 5001 | API trả về `200` và số tiền cần thanh toán theo chính sách | High |
| TC_PAYMENT_002 | Tính cước và thanh toán | Tính cước cho chuyến không tồn tại | Chuyến không tồn tại | 1. Gửi GET `/trips/{tripId}/fare` | tripId = 99999 | API trả về `404` | Medium |
| TC_PAYMENT_003 | Tính cước và thanh toán | Tính cước với tripId sai kiểu dữ liệu | API hoạt động bình thường | 1. Gửi request với tripId không phải số nguyên | tripId = "ABC" | Request bị từ chối do tripId không đúng kiểu dữ liệu | Medium |
| TC_PAYMENT_004 | Tính cước và thanh toán | Thanh toán bằng tiền mặt | Chuyến có số tiền cần thanh toán | 1. Gửi POST `/payments` 2. Chọn phương thức tiền mặt | Payment hợp lệ, phương thức = CASH | API trả về `200`, thanh toán được ghi nhận | High |
| TC_PAYMENT_005 | Tính cước và thanh toán | Thanh toán điện tử thành công | Chuyến có số tiền cần thanh toán và phương thức điện tử được hỗ trợ | 1. Gửi POST `/payments` 2. Chọn phương thức điện tử | Payment hợp lệ | API trả về `200`, giao dịch thanh toán thành công | High |
| TC_PAYMENT_006 | Tính cước và thanh toán | Thanh toán với thông tin không hợp lệ | Chuyến tồn tại | 1. Gửi POST `/payments` với dữ liệu sai | Thông tin thanh toán không hợp lệ | API trả về `400`, thanh toán không được thực hiện | High |

## Scenario 2: Xử lý thanh toán thất bại

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC_PAYMENT_007 | Xử lý thanh toán thất bại | Thanh toán điện tử thất bại | Giao dịch điện tử bị thất bại | 1. Thực hiện thanh toán 2. Kiểm tra trạng thái giao dịch | Payment ID = 7001 | Giao dịch được ghi nhận là thất bại và có thể thực hiện retry theo chính sách | High |
| TC_PAYMENT_008 | Xử lý thanh toán thất bại | Retry giao dịch thất bại thành công | Payment đang ở trạng thái thất bại | 1. Gửi POST `/payments/{paymentId}/retry` | paymentId = 7001 | API trả về `200`, hệ thống thực hiện lại thanh toán | High |
| TC_PAYMENT_009 | Xử lý thanh toán thất bại | Retry payment không được phép | Payment không ở trạng thái có thể retry | 1. Gửi POST `/payments/{paymentId}/retry` | paymentId = 7002 | API trả về `400`, hệ thống không cho retry | High |
| TC_PAYMENT_010 | Xử lý thanh toán thất bại | Retry payment không tồn tại | Payment không tồn tại | 1. Gửi POST `/payments/{paymentId}/retry` | paymentId = 99999 | Hệ thống từ chối yêu cầu retry payment không tồn tại | Medium |
| TC_PAYMENT_011 | Xử lý thanh toán thất bại | Retry với paymentId sai kiểu dữ liệu | API hoạt động bình thường | 1. Gửi request với paymentId không phải số nguyên | paymentId = "ABC" | Request bị từ chối do paymentId không đúng kiểu dữ liệu | Medium |
