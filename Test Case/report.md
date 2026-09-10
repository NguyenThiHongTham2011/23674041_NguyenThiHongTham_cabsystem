# Test Cases - Report API

## Scenario 1: Xem báo cáo hoạt động

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC_REPORT_001 | Xem báo cáo hoạt động | Xem báo cáo với người dùng có quyền | Người quản lý đã đăng nhập và có quyền xem báo cáo | 1. Gửi GET `/reports/operations` | Role = Management | API trả về `200` và báo cáo hoạt động | High |
| TC_REPORT_002 | Xem báo cáo hoạt động | Kiểm tra số lượng chuyến trong báo cáo | Có dữ liệu chuyến trong hệ thống | 1. Gửi GET `/reports/operations` | Dữ liệu chuyến | Báo cáo hiển thị thông tin số lượng chuyến | High |
| TC_REPORT_003 | Xem báo cáo hoạt động | Kiểm tra doanh thu trong báo cáo | Có dữ liệu thanh toán | 1. Gửi GET `/reports/operations` | Dữ liệu giao dịch | Báo cáo hiển thị thông tin doanh thu | High |
| TC_REPORT_004 | Xem báo cáo hoạt động | Kiểm tra tỷ lệ hoàn thành chuyến | Có dữ liệu chuyến | 1. Gửi GET `/reports/operations` | Dữ liệu chuyến hoàn thành | Báo cáo hiển thị tỷ lệ hoàn thành chuyến | Medium |
| TC_REPORT_005 | Xem báo cáo hoạt động | Kiểm tra tỷ lệ hủy chuyến | Có dữ liệu chuyến bị hủy | 1. Gửi GET `/reports/operations` | Dữ liệu chuyến hủy | Báo cáo hiển thị tỷ lệ hủy chuyến | Medium |
| TC_REPORT_006 | Xem báo cáo hoạt động | Kiểm tra hiệu suất tài xế | Có dữ liệu hoạt động của tài xế | 1. Gửi GET `/reports/operations` | Dữ liệu tài xế | Báo cáo hiển thị thông tin hiệu suất tài xế | Medium |
| TC_REPORT_007 | Xem báo cáo hoạt động | Người dùng không có quyền xem báo cáo | Người dùng không có quyền Management | 1. Gửi GET `/reports/operations` | Role không có quyền | API trả về `403`, người dùng không được xem báo cáo | High |
