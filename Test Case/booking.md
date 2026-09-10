# Test Case - Booking API

## Scenario 1: Tạo yêu cầu đặt xe

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC_BOOK_001 | Tạo yêu cầu đặt xe | Tạo yêu cầu đặt xe với thông tin hợp lệ | Khách hàng đã đăng nhập | 1. Gửi POST `/bookings`<br>2. Nhập đầy đủ thông tin<br>3. Gửi request | Điểm đón, điểm đến và loại xe hợp lệ | Yêu cầu đặt xe được tạo thành công, API trả `201` | High |
| TC_BOOK_002 | Tạo yêu cầu đặt xe | Tạo yêu cầu khi thiếu điểm đón | Khách hàng đã đăng nhập | 1. Gửi POST `/bookings`<br>2. Bỏ trống điểm đón<br>3. Gửi request | Thiếu điểm đón | Hệ thống từ chối yêu cầu, API trả `400` | High |
| TC_BOOK_003 | Tạo yêu cầu đặt xe | Tạo yêu cầu khi thiếu điểm đến | Khách hàng đã đăng nhập | 1. Gửi POST `/bookings`<br>2. Bỏ trống điểm đến<br>3. Gửi request | Thiếu điểm đến | Hệ thống từ chối yêu cầu, API trả `400` | High |
| TC_BOOK_004 | Tạo yêu cầu đặt xe | Tạo yêu cầu khi thiếu loại xe | Khách hàng đã đăng nhập | 1. Gửi POST `/bookings`<br>2. Bỏ trống loại xe<br>3. Gửi request | Thiếu loại xe | Hệ thống từ chối yêu cầu, API trả `400` | High |
| TC_BOOK_005 | Tạo yêu cầu đặt xe | Tạo yêu cầu với thông tin không hợp lệ | Khách hàng đã đăng nhập | 1. Gửi POST `/bookings`<br>2. Nhập dữ liệu không hợp lệ<br>3. Gửi request | Dữ liệu booking không hợp lệ | Hệ thống từ chối yêu cầu, API trả `400` | High |

## Scenario 2: Tìm và gửi yêu cầu đến tài xế

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC_BOOK_006 | Tìm và gửi yêu cầu đến tài xế | Tìm tài xế phù hợp cho booking | Booking đã được tạo | 1. Gửi POST `/bookings/{bookingId}/find-driver`<br>2. Nhập bookingId<br>3. Gửi request | bookingId hợp lệ, có tài xế sẵn sàng | Hệ thống tìm được tài xế phù hợp, API trả `200` | High |
| TC_BOOK_007 | Tìm và gửi yêu cầu đến tài xế | Tìm tài xế với booking không tồn tại | Booking không tồn tại | 1. Gửi POST `/bookings/{bookingId}/find-driver`<br>2. Nhập bookingId không tồn tại<br>3. Gửi request | bookingId không tồn tại | Hệ thống không tìm thấy booking, API trả `404` | High |
| TC_BOOK_008 | Tìm và gửi yêu cầu đến tài xế | Tìm tài xế khi không có tài xế phù hợp | Booking đã được tạo | 1. Gửi request tìm tài xế<br>2. Hệ thống thực hiện tìm kiếm | Không có tài xế sẵn sàng/phù hợp | Hệ thống xử lý trường hợp không tìm được tài xế | High |
| TC_BOOK_009 | Tìm và gửi yêu cầu đến tài xế | Gửi yêu cầu chuyến đến tài xế phù hợp | Đã tìm được tài xế | 1. Gửi POST `/bookings/{bookingId}/request-driver`<br>2. Nhập bookingId<br>3. Gửi request | bookingId hợp lệ | Yêu cầu chuyến được gửi đến tài xế, API trả `200` | High |
| TC_BOOK_010 | Tìm và gửi yêu cầu đến tài xế | Gửi yêu cầu với bookingId sai kiểu dữ liệu | Booking tồn tại | 1. Gửi request<br>2. Nhập bookingId không phải số nguyên | bookingId = `ABC` | Request bị từ chối do bookingId không đúng kiểu dữ liệu | Medium |

## Scenario 3: Xử lý phản hồi của tài xế

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC_BOOK_011 | Xử lý phản hồi của tài xế | Tài xế nhận chuyến | Đã gửi yêu cầu chuyến đến tài xế | 1. Gửi POST `/bookings/{bookingId}/driver-response`<br>2. Chọn nhận chuyến<br>3. Gửi request | bookingId hợp lệ, phản hồi accept | Hệ thống xác nhận tài xế nhận chuyến, API trả `200`; không phân công lại tài xế | High |
| TC_BOOK_012 | Xử lý phản hồi của tài xế | Tài xế từ chối chuyến | Đã gửi yêu cầu chuyến đến tài xế | 1. Gửi request phản hồi<br>2. Chọn từ chối chuyến<br>3. Gửi request | bookingId hợp lệ, phản hồi reject | Hệ thống xử lý từ chối và tiếp tục tìm tài xế khác, API trả `200` | High |
| TC_BOOK_013 | Xử lý phản hồi của tài xế | Tài xế không phản hồi yêu cầu | Đã gửi yêu cầu chuyến đến tài xế | 1. Gửi yêu cầu<br>2. Không gửi phản hồi<br>3. Chờ hệ thống xử lý | bookingId hợp lệ, không có phản hồi | Hệ thống tiếp tục tìm tài xế khác mà khách hàng không cần tạo lại yêu cầu | High |
| TC_BOOK_014 | Xử lý phản hồi của tài xế | Phản hồi với bookingId không tồn tại | Không có booking tương ứng | 1. Gửi request phản hồi<br>2. Nhập bookingId không tồn tại | bookingId không tồn tại | Hệ thống không xử lý phản hồi cho booking không tồn tại | Medium |

## Scenario 4: Tìm tài xế thay thế và xử lý không tìm được tài xế

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC_BOOK_015 | Tìm tài xế thay thế và xử lý không tìm được tài xế | Tìm được tài xế thay thế | Tài xế trước đó từ chối hoặc không phản hồi | 1. Gửi POST `/bookings/{bookingId}/alternative-driver`<br>2. Nhập bookingId<br>3. Gửi request | bookingId hợp lệ, có tài xế thay thế | Hệ thống tìm được tài xế thay thế, API trả `200` | High |
| TC_BOOK_016 | Tìm tài xế thay thế và xử lý không tìm được tài xế | Không tìm được tài xế thay thế | Tài xế trước đó từ chối hoặc không phản hồi | 1. Gửi request tìm tài xế thay thế | bookingId hợp lệ, không còn tài xế phù hợp | Hệ thống không tìm được tài xế thay thế, API trả `404` | High |
| TC_BOOK_017 | Tìm tài xế thay thế và xử lý không tìm được tài xế | Xử lý booking khi không còn tài xế | Booking hợp lệ nhưng không có tài xế phù hợp | 1. Gửi POST `/bookings/{bookingId}/no-driver`<br>2. Nhập bookingId<br>3. Gửi request | bookingId hợp lệ | Hệ thống xử lý trạng thái không tìm được tài xế, API trả `200` | High |
| TC_BOOK_018 | Tìm tài xế thay thế và xử lý không tìm được tài xế | Xử lý no-driver với bookingId không hợp lệ | Không có booking tương ứng | 1. Gửi request<br>2. Nhập bookingId không hợp lệ | bookingId không tồn tại | Hệ thống không xử lý yêu cầu cho booking không hợp lệ | Medium |
