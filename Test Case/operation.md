# Test Cases - Operation API

## Scenario 1: Tra cứu dữ liệu vận hành

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC_OPERATION_001 | Tra cứu dữ liệu vận hành | Tra cứu danh sách khách hàng | Nhân viên vận hành đã đăng nhập và có quyền | 1. Gửi GET `/operation/customers` | Không có | API trả về `200` và danh sách khách hàng | High |
| TC_OPERATION_002 | Tra cứu dữ liệu vận hành | Tra cứu danh sách tài xế | Nhân viên vận hành có quyền | 1. Gửi GET `/operation/drivers` | Không có | API trả về `200` và danh sách tài xế | High |
| TC_OPERATION_003 | Tra cứu dữ liệu vận hành | Tra cứu danh sách phương tiện | Nhân viên vận hành có quyền | 1. Gửi GET `/operation/vehicles` | Không có | API trả về `200` và danh sách phương tiện | Medium |
| TC_OPERATION_004 | Tra cứu dữ liệu vận hành | Tra cứu danh sách chuyến | Nhân viên vận hành có quyền | 1. Gửi GET `/operation/trips` | Không có | API trả về `200` và danh sách chuyến | High |
| TC_OPERATION_005 | Tra cứu dữ liệu vận hành | Tra cứu giao dịch | Nhân viên vận hành có quyền | 1. Gửi GET `/operation/transactions` | Không có | API trả về `200` và danh sách giao dịch | High |

## Scenario 2: Xử lý giao dịch và sự cố

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC_OPERATION_006 | Xử lý giao dịch và sự cố | Tạo phiếu xử lý sự cố hợp lệ | Nhân viên vận hành đã đăng nhập và có quyền | 1. Gửi POST `/operation/incidents` | Thông tin sự cố hợp lệ | API trả về `200`, sự cố được ghi nhận thành công | High |
| TC_OPERATION_007 | Xử lý giao dịch và sự cố | Tạo sự cố với thông tin không hợp lệ | Nhân viên vận hành có quyền | 1. Gửi POST `/operation/incidents` | Dữ liệu sự cố không hợp lệ | Hệ thống từ chối dữ liệu sự cố không hợp lệ | Medium |
| TC_OPERATION_008 | Xử lý giao dịch và sự cố | Tra cứu giao dịch sau khi xử lý | Có giao dịch trong hệ thống | 1. Gửi GET `/operation/transactions` | Giao dịch đã xử lý | API trả về `200` và hiển thị thông tin giao dịch | Medium |

## Scenario 3: Kiểm soát quyền vận hành

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC_OPERATION_009 | Kiểm soát quyền vận hành | Nhân viên có quyền truy cập dữ liệu vận hành | Nhân viên có quyền phù hợp | 1. Gửi request đến API vận hành | Role hợp lệ | Hệ thống cho phép truy cập và trả về `200` | High |
| TC_OPERATION_010 | Kiểm soát quyền vận hành | Người dùng không có quyền truy cập | Người dùng không được cấp quyền vận hành | 1. Gửi request đến API vận hành | Role không có quyền | Hệ thống từ chối truy cập | High |
