# Test Case - Auth API

## Scenario 1: Đăng ký tài khoản

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC_AUTH_001 | Đăng ký tài khoản | Đăng ký với thông tin hợp lệ | Người dùng chưa có tài khoản | 1. Gửi POST `/auth/register`<br>2. Nhập đầy đủ thông tin<br>3. Gửi request | Thông tin tài khoản hợp lệ | Tài khoản được đăng ký thành công, API trả `201` | High |
| TC_AUTH_002 | Đăng ký tài khoản | Đăng ký với thông tin không hợp lệ | Người dùng chưa có tài khoản | 1. Gửi POST `/auth/register`<br>2. Nhập dữ liệu không hợp lệ<br>3. Gửi request | Email/số điện thoại/thông tin sai định dạng | Hệ thống từ chối dữ liệu đăng ký | High |
| TC_AUTH_003 | Đăng ký tài khoản | Đăng ký khi thiếu thông tin bắt buộc | Người dùng chưa có tài khoản | 1. Gửi POST `/auth/register`<br>2. Bỏ trống một thông tin cần thiết<br>3. Gửi request | Thiếu thông tin bắt buộc | Hệ thống không tạo tài khoản | Medium |
| TC_AUTH_004 | Đăng ký tài khoản | Đăng ký với tài khoản đã tồn tại | Tài khoản đã tồn tại | 1. Gửi POST `/auth/register`<br>2. Nhập thông tin tài khoản đã tồn tại<br>3. Gửi request | Email/tài khoản đã tồn tại | Hệ thống từ chối đăng ký | High |

## Scenario 2: Đăng nhập

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC_AUTH_005 | Đăng nhập | Đăng nhập với thông tin hợp lệ | Tài khoản đã tồn tại | 1. Gửi POST `/auth/login`<br>2. Nhập thông tin đúng<br>3. Gửi request | Username/password đúng | Đăng nhập thành công, API trả `200` | High |
| TC_AUTH_006 | Đăng nhập | Đăng nhập với sai mật khẩu | Tài khoản đã tồn tại | 1. Gửi POST `/auth/login`<br>2. Nhập username đúng<br>3. Nhập password sai<br>4. Gửi request | Password sai | Hệ thống từ chối đăng nhập | High |
| TC_AUTH_007 | Đăng nhập | Đăng nhập với tài khoản không tồn tại | Không có tài khoản tương ứng | 1. Gửi POST `/auth/login`<br>2. Nhập tài khoản không tồn tại<br>3. Gửi request | Username không tồn tại | Hệ thống từ chối đăng nhập | High |
| TC_AUTH_008 | Đăng nhập | Đăng nhập khi thiếu thông tin | Có API đăng nhập | 1. Gửi POST `/auth/login`<br>2. Bỏ trống username hoặc password<br>3. Gửi request | Thiếu username/password | Hệ thống không cho đăng nhập | Medium |

## Scenario 3: Cập nhật thông tin khách hàng

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC_AUTH_009 | Cập nhật thông tin khách hàng | Cập nhật thông tin với dữ liệu hợp lệ | Khách hàng đã đăng nhập | 1. Gửi PUT `/customers/{customerId}`<br>2. Nhập thông tin mới<br>3. Gửi request | Thông tin khách hàng hợp lệ | Thông tin khách hàng được cập nhật thành công, API trả `200` | High |
| TC_AUTH_010 | Cập nhật thông tin khách hàng | Cập nhật với thông tin không hợp lệ | Khách hàng đã đăng nhập | 1. Gửi PUT `/customers/{customerId}`<br>2. Nhập dữ liệu không hợp lệ<br>3. Gửi request | Dữ liệu không hợp lệ | Hệ thống từ chối cập nhật | Medium |
| TC_AUTH_011 | Cập nhật thông tin khách hàng | Cập nhật với customerId không tồn tại | Khách hàng đã đăng nhập | 1. Gửi PUT `/customers/{customerId}`<br>2. Nhập customerId không tồn tại<br>3. Gửi request | customerId không tồn tại | Hệ thống không cập nhật thông tin khách hàng | High |
| TC_AUTH_012 | Cập nhật thông tin khách hàng | Cập nhật với customerId sai kiểu dữ liệu | API yêu cầu customerId là số nguyên | 1. Gửi PUT `/customers/{customerId}`<br>2. Nhập customerId sai kiểu dữ liệu<br>3. Gửi request | customerId = `ABC` | Request bị từ chối do customerId không đúng kiểu dữ liệu | Medium |
