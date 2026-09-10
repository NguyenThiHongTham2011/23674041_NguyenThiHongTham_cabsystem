# Test Case - Driver API

## Scenario 1: Tài xế phản hồi yêu cầu chuyến

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC_DRIVER_001 | Tài xế phản hồi yêu cầu chuyến | Tài xế nhận chuyến | Tài xế đã đăng nhập và có yêu cầu chuyến | 1. Gửi POST `/drivers/{driverId}/booking-response`<br>2. Nhập driverId<br>3. Chọn nhận chuyến<br>4. Gửi request | driverId hợp lệ, phản hồi accept | Hệ thống xử lý tài xế nhận chuyến, API trả `200` | High |
| TC_DRIVER_002 | Tài xế phản hồi yêu cầu chuyến | Tài xế từ chối chuyến | Tài xế đã đăng nhập và có yêu cầu chuyến | 1. Gửi POST `/drivers/{driverId}/booking-response`<br>2. Nhập driverId<br>3. Chọn từ chối chuyến<br>4. Gửi request | driverId hợp lệ, phản hồi reject | Hệ thống xử lý tài xế từ chối và tiếp tục tìm tài xế khác, API trả `200` | High |
| TC_DRIVER_003 | Tài xế phản hồi yêu cầu chuyến | Phản hồi với driverId không tồn tại | Tài xế không tồn tại | 1. Gửi request<br>2. Nhập driverId không tồn tại | driverId không tồn tại | Hệ thống không xử lý phản hồi cho tài xế không tồn tại | Medium |
| TC_DRIVER_004 | Tài xế phản hồi yêu cầu chuyến | Phản hồi với driverId sai kiểu dữ liệu | API yêu cầu driverId là số nguyên | 1. Gửi request<br>2. Nhập driverId sai kiểu dữ liệu | driverId = `ABC` | Request bị từ chối do driverId không đúng kiểu dữ liệu | Medium |

## Scenario 2: Cập nhật trạng thái chuyến

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC_DRIVER_005 | Cập nhật trạng thái chuyến | Cập nhật trạng thái theo đúng trình tự | Tài xế có chuyến đang thực hiện | 1. Gửi PUT `/drivers/{driverId}/trip-status`<br>2. Nhập driverId<br>3. Cập nhật trạng thái theo đúng trình tự<br>4. Gửi request | Trạng thái chuyến hợp lệ | Trạng thái chuyến được cập nhật thành công, API trả `200` | High |
| TC_DRIVER_006 | Cập nhật trạng thái chuyến | Cập nhật trạng thái sai trình tự | Tài xế có chuyến đang thực hiện | 1. Gửi request cập nhật trạng thái<br>2. Chọn trạng thái không đúng trình tự | Trạng thái không đúng trình tự | Hệ thống từ chối cập nhật, API trả `400` | High |
| TC_DRIVER_007 | Cập nhật trạng thái chuyến | Cập nhật với trạng thái không hợp lệ | Tài xế có chuyến | 1. Gửi request<br>2. Nhập trạng thái không hợp lệ | Status không thuộc trạng thái được quy định | Hệ thống từ chối cập nhật, API trả `400` | High |
| TC_DRIVER_008 | Cập nhật trạng thái chuyến | Cập nhật với driverId không tồn tại | Tài xế không tồn tại | 1. Gửi request<br>2. Nhập driverId không tồn tại | driverId không tồn tại | Hệ thống không cập nhật trạng thái cho tài xế không tồn tại | Medium |
| TC_DRIVER_009 | Cập nhật trạng thái chuyến | Cập nhật với driverId sai kiểu dữ liệu | API yêu cầu driverId là số nguyên | 1. Gửi request<br>2. Nhập driverId sai kiểu dữ liệu | driverId = `ABC` | Request bị từ chối do driverId không đúng kiểu dữ liệu | Medium |

## Scenario 3: Cập nhật vị trí tài xế

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC_DRIVER_010 | Cập nhật vị trí tài xế | Cập nhật vị trí với dữ liệu hợp lệ | Tài xế đã đăng nhập và đang hoạt động | 1. Gửi PUT `/drivers/{driverId}/location`<br>2. Nhập driverId<br>3. Nhập vị trí hiện tại<br>4. Gửi request | driverId hợp lệ, vị trí hợp lệ | Vị trí tài xế được cập nhật thành công, API trả `200` | High |
| TC_DRIVER_011 | Cập nhật vị trí tài xế | Cập nhật vị trí nhiều lần | Tài xế đang hoạt động | 1. Gửi request cập nhật vị trí<br>2. Thay đổi vị trí<br>3. Gửi request lần tiếp theo | Nhiều vị trí hợp lệ | Hệ thống cập nhật vị trí mới của tài xế | Medium |
| TC_DRIVER_012 | Cập nhật vị trí tài xế | Cập nhật vị trí với dữ liệu không hợp lệ | Tài xế đang hoạt động | 1. Gửi request<br>2. Nhập vị trí không hợp lệ | Tọa độ không hợp lệ | Hệ thống từ chối dữ liệu vị trí không hợp lệ | Medium |
| TC_DRIVER_013 | Cập nhật vị trí tài xế | Cập nhật với driverId không tồn tại | Tài xế không tồn tại | 1. Gửi request<br>2. Nhập driverId không tồn tại | driverId không tồn tại | Hệ thống không cập nhật vị trí cho tài xế không tồn tại | Medium |
| TC_DRIVER_014 | Cập nhật vị trí tài xế | Cập nhật với driverId sai kiểu dữ liệu | API yêu cầu driverId là số nguyên | 1. Gửi request<br>2. Nhập driverId sai kiểu dữ liệu | driverId = `ABC` | Request bị từ chối do driverId không đúng kiểu dữ liệu | Medium |

## Scenario 4: Xử lý tài xế nhận hoặc từ chối chuyến

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC_DRIVER_015 | Xử lý tài xế nhận hoặc từ chối chuyến | Tài xế nhận chuyến và không bị phân công lại | Tài xế đã nhận yêu cầu chuyến | 1. Gửi phản hồi nhận chuyến<br>2. Kiểm tra trạng thái phân công | Accept | Hệ thống giữ chuyến cho tài xế đã nhận và không tìm tài xế thay thế | High |
| TC_DRIVER_016 | Xử lý tài xế nhận hoặc từ chối chuyến | Tài xế từ chối và hệ thống tìm tài xế khác | Tài xế đã nhận yêu cầu chuyến | 1. Gửi phản hồi từ chối<br>2. Kiểm tra quá trình tìm tài xế | Reject | Hệ thống tiếp tục tìm tài xế khác mà khách hàng không cần tạo lại yêu cầu | High |
