# Test Cases - History & Rating API

## Scenario 1: Xem lịch sử chuyến

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC_HISTORY_001 | Xem lịch sử chuyến | Xem lịch sử của khách hàng hợp lệ | Khách hàng đã đăng nhập và có lịch sử chuyến | 1. Gửi GET `/customers/{customerId}/trip-history` | customerId = 1001 | API trả về `200` và danh sách lịch sử chuyến của khách hàng | High |
| TC_HISTORY_002 | Xem lịch sử chuyến | Xem lịch sử khi khách hàng chưa có chuyến | Khách hàng tồn tại nhưng chưa có chuyến | 1. Gửi GET `/customers/{customerId}/trip-history` | customerId = 1002 | API trả về `200`, danh sách lịch sử rỗng | Medium |
| TC_HISTORY_003 | Xem lịch sử chuyến | Tra cứu khách hàng không tồn tại | API hoạt động bình thường | 1. Gửi GET `/customers/{customerId}/trip-history` | customerId = 99999 | Hệ thống không trả về lịch sử của khách hàng không tồn tại | Medium |
| TC_HISTORY_004 | Xem lịch sử chuyến | Truyền customerId sai kiểu dữ liệu | API hoạt động bình thường | 1. Gửi request với customerId không phải số nguyên | customerId = "ABC" | Request bị từ chối do customerId không đúng kiểu dữ liệu | Medium |

## Scenario 2: Đánh giá chuyến

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC_HISTORY_005 | Đánh giá chuyến | Đánh giá chuyến đã hoàn thành | Chuyến đã hoàn thành và khách hàng có quyền đánh giá | 1. Gửi POST `/trips/{tripId}/rating` | tripId = 5001, rating hợp lệ | API trả về `201`, đánh giá được lưu thành công | High |
| TC_HISTORY_006 | Đánh giá chuyến | Đánh giá chuyến chưa hoàn thành | Chuyến chưa hoàn thành | 1. Gửi POST `/trips/{tripId}/rating` | tripId = 5002 | API trả về `400`, không cho phép đánh giá chuyến chưa hoàn thành | High |
| TC_HISTORY_007 | Đánh giá chuyến | Đánh giá chuyến không tồn tại | API hoạt động bình thường | 1. Gửi POST `/trips/{tripId}/rating` | tripId = 99999 | Hệ thống từ chối yêu cầu đánh giá chuyến không tồn tại | Medium |
| TC_HISTORY_008 | Đánh giá chuyến | Truyền tripId sai kiểu dữ liệu | API hoạt động bình thường | 1. Gửi request với tripId không phải số nguyên | tripId = "ABC" | Request bị từ chối do tripId không đúng kiểu dữ liệu | Medium |
