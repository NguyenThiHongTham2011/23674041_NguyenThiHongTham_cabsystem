# Test Cases - Trip API

## Scenario 1: Theo dõi trạng thái chuyến

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC_TRIP_001 | Theo dõi trạng thái chuyến | Xem trạng thái chuyến hợp lệ | Chuyến tồn tại và khách hàng có quyền theo dõi | 1. Gửi GET `/trips/{tripId}/status` | tripId = 5001 | API trả về `200` và trạng thái hiện tại của chuyến | High |
| TC_TRIP_002 | Theo dõi trạng thái chuyến | Theo dõi chuyến đang chờ tài xế | Chuyến đang ở trạng thái chờ tìm/nhận tài xế | 1. Gửi GET `/trips/{tripId}/status` | tripId = 5002 | API trả về `200` và trạng thái tương ứng | High |
| TC_TRIP_003 | Theo dõi trạng thái chuyến | Theo dõi chuyến đã được tài xế nhận | Tài xế đã nhận chuyến | 1. Gửi GET `/trips/{tripId}/status` | tripId = 5003 | API trả về `200` và hiển thị trạng thái chuyến đã được nhận | High |
| TC_TRIP_004 | Theo dõi trạng thái chuyến | Theo dõi chuyến đang thực hiện | Chuyến đang được thực hiện | 1. Gửi GET `/trips/{tripId}/status` | tripId = 5004 | API trả về `200` và trạng thái chuyến đang thực hiện | High |
| TC_TRIP_005 | Theo dõi trạng thái chuyến | Theo dõi chuyến đã hoàn thành | Chuyến đã hoàn thành | 1. Gửi GET `/trips/{tripId}/status` | tripId = 5005 | API trả về `200` và trạng thái hoàn thành | Medium |
| TC_TRIP_006 | Theo dõi trạng thái chuyến | Theo dõi chuyến không tồn tại | API hoạt động bình thường | 1. Gửi GET `/trips/{tripId}/status` | tripId = 99999 | API trả về `404` | High |
| TC_TRIP_007 | Theo dõi trạng thái chuyến | Truyền tripId sai kiểu dữ liệu | API hoạt động bình thường | 1. Gửi request với tripId không phải số nguyên | tripId = "ABC" | Request bị từ chối do tripId không đúng kiểu dữ liệu | Medium |
