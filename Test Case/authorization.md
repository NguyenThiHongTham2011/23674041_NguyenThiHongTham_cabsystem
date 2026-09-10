# Test Case - Authorization API

## Scenario 1: Kiểm tra và phân quyền người dùng

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC_AUTHZ_001 | Kiểm tra và phân quyền người dùng | Xem danh sách vai trò | Người dùng đã đăng nhập và có quyền truy cập | 1. Gửi GET `/authorization/roles`<br>2. Gửi request | Tài khoản hợp lệ | Hệ thống trả về danh sách vai trò, API trả `200` | High |
| TC_AUTHZ_002 | Kiểm tra và phân quyền người dùng | Kiểm tra quyền được phép thực hiện chức năng | Người dùng đã đăng nhập và được cấp quyền | 1. Gửi POST `/authorization/check`<br>2. Nhập thông tin quyền cần kiểm tra<br>3. Gửi request | Permission được cấp cho người dùng | Hệ thống xác nhận người dùng có quyền thực hiện chức năng, API trả `200` | High |
| TC_AUTHZ_003 | Kiểm tra và phân quyền người dùng | Kiểm tra quyền không được phép thực hiện chức năng | Người dùng đã đăng nhập nhưng không được cấp quyền | 1. Gửi POST `/authorization/check`<br>2. Nhập quyền không được cấp<br>3. Gửi request | Permission không được cấp | Hệ thống từ chối quyền thực hiện chức năng, API trả `403` | High |
| TC_AUTHZ_004 | Kiểm tra và phân quyền người dùng | Kiểm tra với quyền không tồn tại | Người dùng đã đăng nhập | 1. Gửi POST `/authorization/check`<br>2. Nhập permission không tồn tại<br>3. Gửi request | Permission không tồn tại | Hệ thống không xác nhận quyền cho permission không tồn tại | Medium |
| TC_AUTHZ_005 | Kiểm tra và phân quyền người dùng | Kiểm tra quyền khi người dùng chưa xác thực | Người dùng chưa đăng nhập | 1. Gửi POST `/authorization/check`<br>2. Không cung cấp thông tin xác thực<br>3. Gửi request | Không có thông tin xác thực | Hệ thống không cho phép kiểm tra/thực hiện quyền khi chưa xác thực | High |

## Scenario 2: Ghi nhận và xem audit log

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC_AUTHZ_006 | Ghi nhận và xem audit log | Ghi nhận audit log khi thực hiện thao tác quan trọng | Người dùng có quyền thực hiện thao tác | 1. Thực hiện thao tác quan trọng<br>2. Gửi request thành công<br>3. Kiểm tra audit log | Thao tác quản trị quan trọng | Hệ thống ghi nhận thao tác vào audit log | High |
| TC_AUTHZ_007 | Ghi nhận và xem audit log | Ghi nhận audit log cho nhiều thao tác | Người dùng có quyền thực hiện thao tác | 1. Thực hiện nhiều thao tác quan trọng<br>2. Kiểm tra audit log | Nhiều thao tác quan trọng | Các thao tác được ghi nhận tương ứng trong audit log | Medium |
| TC_AUTHZ_008 | Ghi nhận và xem audit log | Xem audit log với người dùng có quyền | Người dùng đã đăng nhập và có quyền xem audit log | 1. Gửi GET `/authorization/audit-logs`<br>2. Gửi request | Tài khoản có quyền xem log | Hệ thống trả về danh sách audit log, API trả `200` | High |
| TC_AUTHZ_009 | Ghi nhận và xem audit log | Xem audit log khi không có quyền | Người dùng đã đăng nhập nhưng không có quyền xem log | 1. Gửi GET `/authorization/audit-logs`<br>2. Gửi request | Tài khoản không có quyền | Hệ thống từ chối truy cập, API trả `403` | High |
| TC_AUTHZ_010 | Ghi nhận và xem audit log | Xem audit log khi chưa xác thực | Người dùng chưa đăng nhập | 1. Gửi GET `/authorization/audit-logs`<br>2. Gửi request | Không có thông tin xác thực | Người dùng không được phép truy cập audit log | High |
