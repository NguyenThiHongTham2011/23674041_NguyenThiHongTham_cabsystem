

## B1 – Ngữ cảnh nghiệp vụ và vấn đề nghiệp vụ
Business Context
| **Nội dung**           | **Mô tả**                                              |
| ---------------------- | ------------------------------------------------------ |
| **Tên hệ thống**       | CAB System – Nền tảng đặt xe                           |
| **Doanh nghiệp**       | Công ty ABC                                            |
| **Mục đích**           | Cung cấp dịch vụ đặt xe trực tuyến cho khách hàng      |
| **Khách hàng**         | Đặt xe, theo dõi chuyến, thanh toán và đánh giá tài xế |
| **Tài xế**             | Nhận chuyến, thực hiện chuyến và cập nhật trạng thái   |
| **Nhân viên vận hành** | Quản lý khách hàng, tài xế, phương tiện và chuyến đi   |
| **Ban lãnh đạo**       | Theo dõi báo cáo và hiệu quả kinh doanh                |
| **Hệ thống bên ngoài** | Nhà cung cấp thanh toán và nhà cung cấp thông báo      |

Business Problems
| **Mã**   | **Vấn đề nghiệp vụ**              | **Hệ quả**                               |
| -------- | --------------------------------- | ---------------------------------------- |
| **BP01** | Phân công tài xế còn thủ công     | Điều phối xe chưa tự động và khó mở rộng |
| **BP02** | Khó theo dõi trạng thái chuyến    | Thiếu khả năng theo dõi chuyến           |
| **BP03** | Thanh toán chưa quản lý tập trung | Tính cước và thanh toán chưa thống nhất  |
| **BP04** | Khó mở rộng hệ thống              | Nền tảng thiếu khả năng mở rộng          |
| **BP05** | Thông báo chưa linh hoạt          | Khó mở rộng kênh thông báo               |
| **BP06** | Thiếu công cụ quản lý vận hành    | Thiếu công cụ giám sát tập trung         |
| **BP07** | Thiếu dữ liệu và báo cáo          | Thiếu dữ liệu phục vụ quản lý            |

```mermaid
flowchart TD

    A["Công ty ABC<br/>Dịch vụ đặt xe trực tuyến"]

    A --> B["Nghiệp vụ hiện tại"]

    B --> B1["Khách hàng đặt xe"]
    B1 --> B2["Tìm tài xế"]
    B2 --> B3["Tài xế nhận chuyến"]
    B3 --> B4["Thực hiện chuyến"]
    B4 --> B5["Tính cước"]
    B5 --> B6["Thanh toán"]
    B6 --> B7["Đánh giá"]

    A --> C["Các vấn đề nghiệp vụ"]

    C --> C1["Phân công tài xế còn thủ công"]
    C --> C2["Khó theo dõi trạng thái chuyến"]
    C --> C3["Thanh toán chưa quản lý tập trung"]
    C --> C4["Khó mở rộng hệ thống"]
    C --> C5["Thông báo chưa linh hoạt"]
    C --> C6["Thiếu công cụ quản lý vận hành"]
    C --> C7["Thiếu dữ liệu và báo cáo"]

    C1 --> P1["Điều phối xe chưa tự động và khó mở rộng"]
    C2 --> P2["Thiếu khả năng theo dõi chuyến"]
    C3 --> P3["Tính cước và thanh toán chưa thống nhất"]
    C4 --> P4["Nền tảng thiếu khả năng mở rộng"]
    C5 --> P5["Khó mở rộng kênh thông báo"]
    C6 --> P6["Thiếu công cụ giám sát tập trung"]
    C7 --> P7["Thiếu dữ liệu phục vụ quản lý"]

    A --> D["Mục tiêu"]
    D --> D1["Xây dựng nền tảng CAB mới"]
    D1 --> D2["Tự động hóa đặt xe và điều phối"]
    D1 --> D3["Quản lý thanh toán tập trung"]
    D1 --> D4["Hỗ trợ vận hành và báo cáo"]
    D1 --> D5["Có khả năng mở rộng"]
```

---

# B2 – Stakeholder
Stakeholder List
| **Mã**   | **Stakeholder**         | **Vai trò / Mối quan tâm**                      |
| -------- | ----------------------- | ----------------------------------------------- |
| **ST01** | Khách hàng              | Đặt xe, theo dõi chuyến, thanh toán và đánh giá |
| **ST02** | Tài xế                  | Nhận / từ chối và thực hiện chuyến              |
| **ST03** | Nhân viên vận hành      | Quản lý và xử lý sự cố                          |
| **ST04** | Ban giám đốc            | Mục tiêu kinh doanh và báo cáo                  |
| **ST05** | Business Analyst        | Thu thập và xác nhận yêu cầu                    |
| **ST06** | Đội phát triển          | Xây dựng và triển khai                          |
| **ST07** | Nhà cung cấp thanh toán | Xử lý thanh toán điện tử                        |
| **ST08** | Nhà cung cấp thông báo  | Cung cấp dịch vụ thông báo                      |
Stakeholder Matrix
| **Stakeholder**         | **Quyền lực** | **Mức độ quan tâm** | **Cách quản lý**              |
| ----------------------- | ------------- | ------------------- | ----------------------------- |
| Ban giám đốc            | Cao           | Cao                 | Quản lý chặt chẽ              |
| Nhân viên vận hành      | Cao           | Cao                 | Quản lý chặt chẽ              |
| Khách hàng              | Thấp          | Cao                 | Theo dõi và thu thập phản hồi |
| Tài xế                  | Thấp          | Cao                 | Theo dõi và thu thập phản hồi |
| Business Analyst        | Trung bình    | Cao                 | Phối hợp thường xuyên         |
| Đội phát triển          | Trung bình    | Trung bình          | Phối hợp khi cần              |
| Nhà cung cấp thanh toán | Thấp          | Thấp                | Theo dõi                      |
| Nhà cung cấp thông báo  | Thấp          | Thấp                | Theo dõi                      |

```mermaid
flowchart LR

    S["CAB System"]

    S --- KH["Khách hàng<br/>Đặt xe, theo dõi chuyến,<br/>thanh toán, đánh giá"]

    S --- TX["Tài xế<br/>Nhận/từ chối và thực hiện chuyến"]

    S --- NV["Nhân viên vận hành<br/>Quản lý và xử lý sự cố"]

    S --- BG["Ban giám đốc<br/>Mục tiêu kinh doanh và báo cáo"]

    S --- BA["Business Analyst<br/>Thu thập và xác nhận yêu cầu"]

    S --- DEV["Đội phát triển<br/>Xây dựng và triển khai"]

    S --- PAY["Nhà cung cấp thanh toán<br/>Xử lý thanh toán điện tử"]

    S --- NOTI["Nhà cung cấp thông báo<br/>Cung cấp dịch vụ thông báo"]
```

### Stakeholder Matrix

```mermaid
quadrantChart
    title Stakeholder Matrix - CAB System
    x-axis "Quan tâm thấp" --> "Quan tâm cao"
    y-axis "Quyền lực thấp" --> "Quyền lực cao"

    "Ban giám đốc": [0.75, 0.90]
    "Nhân viên vận hành": [0.90, 0.80]
    "Khách hàng": [0.85, 0.40]
    "Tài xế": [0.80, 0.35]
    "BA": [0.65, 0.55]
    "Đội phát triển": [0.45, 0.50]
    "Nhà cung cấp thanh toán": [0.30, 0.40]
    "Nhà cung cấp thông báo": [0.25, 0.30]
```

---

# B3 – Business Goal
| **Mã BG** | **Business Goal**                 |
| :-------: | --------------------------------- |
|  **BG01** | Tự động tìm và điều phối tài xế   |
|  **BG02** | Thanh toán tiền mặt và trực tuyến |
|  **BG03** | Quản lý và theo dõi chuyến đi     |
|  **BG04** | Quản lý tài khoản và người dùng   |
|  **BG05** | Hỗ trợ vận hành                   |
|  **BG06** | Cung cấp thông báo                |
|  **BG07** | Cung cấp báo cáo quản trị         |
|  **BG08** | Ổn định và mở rộng                |
|  **BG09** | An toàn và bảo mật                |
|  **BG10** | Mở rộng chức năng tương lai       |

```mermaid
mindmap
  root((Business Goals))
    BG01["Tự động tìm và điều phối tài xế"]
    BG02["Thanh toán tiền mặt và trực tuyến"]
    BG03["Quản lý và theo dõi chuyến đi"]
    BG04["Quản lý tài khoản và người dùng"]
    BG05["Hỗ trợ vận hành"]
    BG06["Cung cấp thông báo"]
    BG07["Cung cấp báo cáo quản trị"]
    BG08["Ổn định và mở rộng"]
    BG09["An toàn và bảo mật"]
    BG10["Mở rộng chức năng tương lai"]
```

---

# B4 – Scope
In Scope – Phạm vi phải làm
| **STT** | **Chức năng**           |
| :-----: | ----------------------- |
|    1    | Quản lý tài khoản       |
|    2    | Đặt xe                  |
|    3    | Tìm và điều phối tài xế |
|    4    | Nhận / từ chối chuyến   |
|    5    | Theo dõi chuyến         |
|    6    | Thực hiện chuyến        |
|    7    | Tính cước               |
|    8    | Thanh toán              |
|    9    | Thông báo               |
|    10   | Quản trị vận hành       |
|    11   | Báo cáo                 |
|    12   | Bảo mật và phân quyền   |
Out of Scope – Không nên làm
| **STT** | **Nội dung**                          |
| :-----: | ------------------------------------- |
|    1    | Tự xây hệ thống thanh toán            |
|    2    | Lưu thông tin thẻ trực tiếp           |
|    3    | Tự xây hệ thống bản đồ GPS            |
|    4    | Xây ứng dụng cho nhà cung cấp         |
|    5    | Tự xây hạ tầng SMS / Email / Push     |
|    6    | Tự quyết định cách tính cước          |
|    7    | Tự quyết định tiêu chí ưu tiên tài xế |
|    8    | Tự quyết định chính sách hủy          |
|    9    | Tự quyết định thời gian phản hồi      |
|    10   | Triển khai dịch vụ mới ngay           |

```mermaid
flowchart LR

    subgraph IN["PHẠM VI PHẢI LÀM"]
        A1["Quản lý tài khoản"]
        A2["Đặt xe"]
        A3["Tìm và điều phối tài xế"]
        A4["Nhận / từ chối chuyến"]
        A5["Theo dõi chuyến"]
        A6["Thực hiện chuyến"]
        A7["Tính cước"]
        A8["Thanh toán"]
        A9["Thông báo"]
        A10["Quản trị vận hành"]
        A11["Báo cáo"]
        A12["Bảo mật và phân quyền"]
    end

    subgraph OUT["KHÔNG NÊN LÀM"]
        B1["Tự xây hệ thống thanh toán"]
        B2["Lưu thông tin thẻ trực tiếp"]
        B3["Tự xây hệ thống bản đồ GPS"]
        B4["Xây ứng dụng cho nhà cung cấp"]
        B5["Tự xây hạ tầng SMS / Email / Push"]
        B6["Tự quyết định cách tính cước"]
        B7["Tự quyết định tiêu chí ưu tiên tài xế"]
        B8["Tự quyết định chính sách hủy"]
        B9["Tự quyết định thời gian phản hồi"]
        B10["Triển khai dịch vụ mới ngay"]
    end
```

---

# B5 – Business Requirement
| **Mã BR** | **Business Requirement**   |
| :-------: | -------------------------- |
|  **BR01** | Tự động tìm tài xế         |
|  **BR02** | Đặt xe                     |
|  **BR03** | Quản lý nhận chuyến        |
|  **BR04** | Tìm tài xế thay thế        |
|  **BR05** | Theo dõi chuyến            |
|  **BR06** | Cập nhật trạng thái chuyến |
|  **BR07** | Tính cước                  |
|  **BR08** | Thanh toán                 |
|  **BR09** | Thông báo                  |
|  **BR10** | Quản lý vận hành           |
|  **BR11** | Báo cáo                    |
|  **BR12** | Bảo mật và phân quyền      |
|  **BR13** | Khả năng mở rộng           |

```mermaid
mindmap
    root((Business Requirement))
        BR01["Tự động tìm tài xế"]
        BR02["Đặt xe"]
        BR03["Quản lý nhận chuyến"]
        BR04["Tìm tài xế thay thế"]
        BR05["Theo dõi chuyến"]
        BR06["Cập nhật trạng thái chuyến"]
        BR07["Tính cước"]
        BR08["Thanh toán"]
        BR09["Thông báo"]
        BR10["Quản lý vận hành"]
        BR11["Báo cáo"]
        BR12["Bảo mật và phân quyền"]
        BR13["Khả năng mở rộng"]
```

---

# B6 – Business Process
| **Mã BP** | **Tên quy trình**           | **Mô tả ngắn**                       |
| :-------: | --------------------------- | ------------------------------------ |
|  **BP01** | Đăng ký & quản lý tài khoản | Người dùng tạo và quản lý tài khoản  |
|  **BP02** | Đặt xe                      | Khách hàng tạo yêu cầu đặt xe        |
|  **BP03** | Tìm & điều phối tài xế      | Hệ thống tìm và phân công tài xế     |
|  **BP04** | Nhận / từ chối chuyến       | Tài xế xử lý yêu cầu chuyến          |
|  **BP05** | Thực hiện & theo dõi chuyến | Tài xế thực hiện và cập nhật chuyến  |
|  **BP06** | Tính cước & thanh toán      | Tính số tiền và thực hiện thanh toán |
|  **BP07** | Gửi thông báo               | Gửi thông báo đến người dùng         |
|  **BP08** | Đánh giá sau chuyến         | Khách hàng đánh giá tài xế           |
|  **BP09** | Quản lý vận hành            | Nhân viên vận hành quản lý hệ thống  |
|  **BP10** | Báo cáo & quản trị          | Cung cấp dữ liệu và báo cáo          |

```mermaid
flowchart TD

    BP01["BP01<br/>Đăng ký & quản lý tài khoản"]
    BP02["BP02<br/>Đặt xe"]
    BP03["BP03<br/>Tìm & điều phối tài xế"]
    BP04["BP04<br/>Nhận / từ chối chuyến"]
    BP05["BP05<br/>Thực hiện & theo dõi chuyến"]
    BP06["BP06<br/>Tính cước & thanh toán"]
    BP07["BP07<br/>Gửi thông báo"]
    BP08["BP08<br/>Đánh giá sau chuyến"]
    BP09["BP09<br/>Quản lý vận hành"]
    BP10["BP10<br/>Báo cáo & quản trị"]

    BP01 --> BP02
    BP02 --> BP03
    BP03 --> BP04

    BP04 -->|Nhận| BP05
    BP04 -->|Từ chối / không phản hồi| BP03

    BP05 --> BP06
    BP06 --> BP07
    BP05 --> BP08

    BP09 --> BP10
```

---

# B7 – Functional Requirement
| **Mã FR** | **Functional Requirement**      |
| :-------: | ------------------------------- |
|  **FR01** | Đăng ký tài khoản               |
|  **FR02** | Đăng nhập                       |
|  **FR03** | Quản lý thông tin cá nhân       |
|  **FR04** | Tạo yêu cầu đặt xe              |
|  **FR05** | Tìm tài xế phù hợp              |
|  **FR06** | Gửi yêu cầu đến tài xế          |
|  **FR07** | Nhận / từ chối chuyến           |
|  **FR08** | Tìm tài xế thay thế             |
|  **FR09** | Thông báo không tìm được tài xế |
|  **FR10** | Theo dõi trạng thái chuyến      |
|  **FR11** | Cập nhật trạng thái chuyến      |
|  **FR12** | Cập nhật vị trí tài xế          |
|  **FR13** | Tính cước                       |
|  **FR14** | Thanh toán                      |
|  **FR15** | Xử lý thanh toán thất bại       |
|  **FR16** | Gửi thông báo                   |
|  **FR17** | Xem lịch sử chuyến              |
|  **FR18** | Đánh giá tài xế                 |
|  **FR19** | Quản lý vận hành                |
|  **FR20** | Tra cứu giao dịch               |
|  **FR21** | Xử lý sự cố                     |
|  **FR22** | Báo cáo hoạt động               |
|  **FR23** | Phân quyền                      |

```mermaid
mindmap
    root((Functional Requirement))
        FR01["Đăng ký tài khoản"]
        FR02["Đăng nhập"]
        FR03["Quản lý thông tin cá nhân"]
        FR04["Tạo yêu cầu đặt xe"]
        FR05["Tìm tài xế phù hợp"]
        FR06["Gửi yêu cầu đến tài xế"]
        FR07["Nhận / từ chối chuyến"]
        FR08["Tìm tài xế thay thế"]
        FR09["Thông báo không tìm được tài xế"]
        FR10["Theo dõi trạng thái chuyến"]
        FR11["Cập nhật trạng thái chuyến"]
        FR12["Cập nhật vị trí tài xế"]
        FR13["Tính cước"]
        FR14["Thanh toán"]
        FR15["Xử lý thanh toán thất bại"]
        FR16["Gửi thông báo"]
        FR17["Xem lịch sử chuyến"]
        FR18["Đánh giá tài xế"]
        FR19["Quản lý vận hành"]
        FR20["Tra cứu giao dịch"]
        FR21["Xử lý sự cố"]
        FR22["Báo cáo hoạt động"]
        FR23["Phân quyền"]
```

---

# B8 – Business Rule + Exception
Business Rules
|   **Mã**  | **Business Rule**      |
| :-------: | ---------------------- |
| **BRU01** | Tài xế phải sẵn sàng   |
| **BRU02** | Ưu tiên tài xế phù hợp |
| **BRU03** | Tài xế nhận chuyến     |
| **BRU04** | Tài xế từ chối         |
| **BRU05** | Không phản hồi         |
| **BRU06** | Không tìm được tài xế  |
| **BRU07** | Trình tự trạng thái    |
| **BRU08** | Tính cước              |
| **BRU09** | Thanh toán             |
| **BRU10** | Bảo mật thanh toán     |
| **BRU11** | Đánh giá sau chuyến    |
| **BRU12** | Phân quyền             |
| **BRU13** | Lưu vết                |
Exception
|  **Mã**  | **Exception**         |
| :------: | --------------------- |
| **EX01** | Không tìm thấy tài xế |
| **EX02** | Tài xế từ chối        |
| **EX03** | Tài xế không phản hồi |
| **EX04** | Thanh toán thất bại   |
| **EX05** | Mất kết nối           |
| **EX06** | Chuyến bị lỗi         |
| **EX07** | Không có quyền        |


```mermaid
flowchart TD

    subgraph RULE["BUSINESS RULE"]
        R1["BRU01<br/>Tài xế phải sẵn sàng"]
        R2["BRU02<br/>Ưu tiên tài xế phù hợp"]
        R3["BRU03<br/>Tài xế nhận chuyến"]
        R4["BRU04<br/>Tài xế từ chối"]
        R5["BRU05<br/>Không phản hồi"]
        R6["BRU06<br/>Không tìm được tài xế"]
        R7["BRU07<br/>Trình tự trạng thái"]
        R8["BRU08<br/>Tính cước"]
        R9["BRU09<br/>Thanh toán"]
        R10["BRU10<br/>Bảo mật thanh toán"]
        R11["BRU11<br/>Đánh giá sau chuyến"]
        R12["BRU12<br/>Phân quyền"]
        R13["BRU13<br/>Lưu vết"]
    end

    subgraph EX["EXCEPTION"]
        E1["EX01<br/>Không tìm thấy tài xế"]
        E2["EX02<br/>Tài xế từ chối"]
        E3["EX03<br/>Tài xế không phản hồi"]
        E4["EX04<br/>Thanh toán thất bại"]
        E5["EX05<br/>Mất kết nối"]
        E6["EX06<br/>Chuyến bị lỗi"]
        E7["EX07<br/>Không có quyền"]
    end
```

---

# B9 – Data Modeling / ERD
Entity List
| **Entity**            | **Mục đích**                   |
| --------------------- | ------------------------------ |
| **CUSTOMER**          | Lưu thông tin khách hàng       |
| **DRIVER**            | Lưu thông tin tài xế           |
| **VEHICLE**           | Lưu thông tin phương tiện      |
| **SERVICE**           | Lưu loại dịch vụ               |
| **TRIP**              | Lưu thông tin chuyến đi        |
| **DRIVER_ASSIGNMENT** | Lưu thông tin phân công tài xế |
| **PAYMENT**           | Lưu thông tin thanh toán       |
| **RATING**            | Lưu đánh giá chuyến đi         |
| **NOTIFICATION**      | Lưu thông tin thông báo        |
Entity Attributes
| **Entity**            | **Attributes**                                                                                          |
| --------------------- | ------------------------------------------------------------------------------------------------------- |
| **CUSTOMER**          | customer_id (PK), name, phone, email                                                                    |
| **DRIVER**            | driver_id (PK), name, phone, status                                                                     |
| **VEHICLE**           | vehicle_id (PK), driver_id (FK), license_plate, vehicle_type                                            |
| **SERVICE**           | service_id (PK), service_name                                                                           |
| **TRIP**              | trip_id (PK), customer_id (FK), service_id (FK), pickup_location, destination, status, fare, created_at |
| **DRIVER_ASSIGNMENT** | assignment_id (PK), trip_id (FK), driver_id (FK), status, assigned_at, responded_at                     |
| **PAYMENT**           | payment_id (PK), trip_id (FK), amount, method, status                                                   |
| **RATING**            | rating_id (PK), trip_id (FK), score, comment                                                            |
| **NOTIFICATION**      | notification_id (PK), recipient_type, recipient_id, content, status                                     |
Relationships
| **Entity 1** | **Quan hệ** | **Entity 2**      |
| ------------ | :---------: | ----------------- |
| CUSTOMER     |    1 – N    | TRIP              |
| SERVICE      |    1 – N    | TRIP              |
| TRIP         |    1 – N    | DRIVER_ASSIGNMENT |
| DRIVER       |    1 – N    | DRIVER_ASSIGNMENT |
| DRIVER       |    1 – N    | VEHICLE           |
| TRIP         |    1 – 1    | PAYMENT           |
| TRIP         |   1 – 0/1   | RATING            |
| CUSTOMER     |    1 – N    | NOTIFICATION      |
| DRIVER       |    1 – N    | NOTIFICATION      |

```mermaid
erDiagram

    CUSTOMER ||--o{ TRIP : creates
    SERVICE ||--o{ TRIP : uses

    TRIP ||--o{ DRIVER_ASSIGNMENT : has
    DRIVER ||--o{ DRIVER_ASSIGNMENT : receives

    DRIVER ||--o{ VEHICLE : uses

    TRIP ||--|| PAYMENT : has
    TRIP ||--o| RATING : receives

    CUSTOMER ||--o{ NOTIFICATION : receives
    DRIVER ||--o{ NOTIFICATION : receives

    CUSTOMER {
        int customer_id PK
        string name
        string phone
        string email
    }

    DRIVER {
        int driver_id PK
        string name
        string phone
        string status
    }

    VEHICLE {
        int vehicle_id PK
        int driver_id FK
        string license_plate
        string vehicle_type
    }

    SERVICE {
        int service_id PK
        string service_name
    }

    TRIP {
        int trip_id PK
        int customer_id FK
        int service_id FK
        string pickup_location
        string destination
        string status
        decimal fare
        datetime created_at
    }

    DRIVER_ASSIGNMENT {
        int assignment_id PK
        int trip_id FK
        int driver_id FK
        string status
        datetime assigned_at
        datetime responded_at
    }

    PAYMENT {
        int payment_id PK
        int trip_id FK
        decimal amount
        string method
        string status
    }

    RATING {
        int rating_id PK
        int trip_id FK
        int score
        string comment
    }

    NOTIFICATION {
        int notification_id PK
        string recipient_type
        int recipient_id
        string content
        string status
    }
```

---

# B10 – Non-functional Requirement
| **Mã NFR** | **Nhóm**                   | **Non-functional Requirement**                            |
| :--------: | -------------------------- | --------------------------------------------------------- |
|  **NFR01** | Hiệu năng                  | Hệ thống có thời gian phản hồi phù hợp                    |
|  **NFR02** | Khả năng mở rộng           | Hệ thống có khả năng mở rộng khi số lượng người dùng tăng |
|  **NFR03** | Tính sẵn sàng              | Hệ thống hoạt động ổn định                                |
|  **NFR04** | Khả năng phục hồi          | Lỗi ở một thành phần không làm dừng toàn bộ hệ thống      |
|  **NFR05** | Bảo mật                    | Bảo vệ dữ liệu người dùng và giao dịch                    |
|  **NFR06** | Xác thực & phân quyền      | Kiểm soát quyền truy cập theo vai trò                     |
|  **NFR07** | Khả năng tích hợp          | Có khả năng tích hợp với dịch vụ bên ngoài                |
|  **NFR08** | Khả năng bảo trì           | Có thể bảo trì và thay đổi các thành phần                 |
|  **NFR09** | Khả năng mở rộng chức năng | Có thể bổ sung chức năng mới                              |
|  **NFR10** | Lưu vết & kiểm toán        | Lưu log các thao tác quan trọng                           |

```mermaid
mindmap
    root((Non-functional Requirement))
        NFR01["Hiệu năng"]
        NFR02["Khả năng mở rộng"]
        NFR03["Tính sẵn sàng"]
        NFR04["Khả năng phục hồi"]
        NFR05["Bảo mật"]
        NFR06["Xác thực & phân quyền"]
        NFR07["Khả năng tích hợp"]
        NFR08["Khả năng bảo trì"]
        NFR09["Khả năng mở rộng chức năng"]
        NFR10["Lưu vết & kiểm toán"]
```

---

# B11 – Use Case Diagram
Use Case List
| **Mã UC** | **Use Case**           | **Actor chính**                     |
| :-------: | ---------------------- | ----------------------------------- |
|  **UC01** | Quản lý tài khoản      | Khách hàng, Tài xế                  |
|  **UC02** | Đặt xe                 | Khách hàng                          |
|  **UC03** | Tìm & phân công tài xế | Nhân viên vận hành                  |
|  **UC04** | Nhận / từ chối chuyến  | Tài xế                              |
|  **UC05** | Thực hiện chuyến       | Tài xế                              |
|  **UC06** | Theo dõi chuyến        | Khách hàng, Nhân viên vận hành      |
|  **UC07** | Tính cước              | Hệ thống                            |
|  **UC08** | Thanh toán             | Khách hàng, Nhà cung cấp thanh toán |
|  **UC09** | Gửi thông báo          | Hệ thống, Nhà cung cấp thông báo    |
|  **UC10** | Xem lịch sử chuyến     | Khách hàng                          |
|  **UC11** | Đánh giá tài xế        | Khách hàng                          |
|  **UC12** | Quản lý vận hành       | Nhân viên vận hành                  |
|  **UC13** | Xử lý sự cố            | Nhân viên vận hành                  |
|  **UC14** | Tra cứu giao dịch      | Nhân viên vận hành                  |
|  **UC15** | Xem báo cáo            | Ban lãnh đạo, Nhân viên vận hành    |
Actors
| **Actor**                   | **Vai trò**                                   |
| --------------------------- | --------------------------------------------- |
| **Khách hàng**              | Đặt xe, theo dõi chuyến, thanh toán, đánh giá |
| **Tài xế**                  | Nhận / từ chối và thực hiện chuyến            |
| **Nhân viên vận hành**      | Quản lý và xử lý sự cố                        |
| **Ban lãnh đạo**            | Theo dõi mục tiêu kinh doanh và báo cáo       |
| **Nhà cung cấp thanh toán** | Xử lý thanh toán điện tử                      |
| **Nhà cung cấp thông báo**  | Cung cấp dịch vụ thông báo                    |
Use Case Relationships
| **Use Case**                  | **Quan hệ** | **Use Case được liên kết**    |
| ----------------------------- | :---------: | ----------------------------- |
| UC02 – Đặt xe                 |  `include`  | UC03 – Tìm & phân công tài xế |
| UC03 – Tìm & phân công tài xế |  `include`  | UC09 – Gửi thông báo          |
| UC05 – Thực hiện chuyến       |  `include`  | UC07 – Tính cước              |
| UC07 – Tính cước              |  `include`  | UC08 – Thanh toán             |
| UC08 – Thanh toán             |  `include`  | UC09 – Gửi thông báo          |
| UC05 – Thực hiện chuyến       |  `include`  | UC09 – Gửi thông báo          |

```mermaid
flowchart LR

    KH["👤 Khách hàng"]
    TX["🚗 Tài xế"]
    NV["👨‍💼 Nhân viên vận hành"]
    GD["👔 Ban lãnh đạo"]
    PAY["💳 Nhà cung cấp thanh toán"]
    NOTI["🔔 Nhà cung cấp thông báo"]

    subgraph CAB["CAB SYSTEM - Nền tảng đặt xe"]

        UC01(["UC01<br/>Quản lý tài khoản"])
        UC02(["UC02<br/>Đặt xe"])
        UC03(["UC03<br/>Tìm & phân công tài xế"])
        UC04(["UC04<br/>Nhận / từ chối chuyến"])
        UC05(["UC05<br/>Thực hiện chuyến"])
        UC06(["UC06<br/>Theo dõi chuyến"])
        UC07(["UC07<br/>Tính cước"])
        UC08(["UC08<br/>Thanh toán"])
        UC09(["UC09<br/>Gửi thông báo"])
        UC10(["UC10<br/>Xem lịch sử chuyến"])
        UC11(["UC11<br/>Đánh giá tài xế"])
        UC12(["UC12<br/>Quản lý vận hành"])
        UC13(["UC13<br/>Xử lý sự cố"])
        UC14(["UC14<br/>Tra cứu giao dịch"])
        UC15(["UC15<br/>Xem báo cáo"])

    end

    KH --> UC01
    KH --> UC02
    KH --> UC06
    KH --> UC08
    KH --> UC10
    KH --> UC11

    TX --> UC01
    TX --> UC04
    TX --> UC05
    TX --> UC06

    NV --> UC03
    NV --> UC06
    NV --> UC12
    NV --> UC13
    NV --> UC14
    NV --> UC15

    GD --> UC15

    PAY --> UC08
    NOTI --> UC09

    UC02 -.->|include| UC03
    UC03 -.->|include| UC09
    UC05 -.->|include| UC07
    UC07 -.->|include| UC08
    UC08 -.->|include| UC09
    UC05 -.->|include| UC09
```

### B12 – Requirement Traceability

```mermaid
flowchart LR
    BG01["BG01<br/>Tự động tìm & điều phối tài xế"]
    BG02["BG02<br/>Thanh toán tiền mặt & trực tuyến"]
    BG03["BG03<br/>Quản lý & theo dõi chuyến"]
    BG04["BG04<br/>Quản lý tài khoản"]
    BG05["BG05<br/>Hỗ trợ vận hành"]
    BG06["BG06<br/>Thông báo"]
    BG07["BG07<br/>Báo cáo quản trị"]
    BG08["BG08<br/>Ổn định & mở rộng"]
    BG09["BG09<br/>Bảo mật"]
    BG10["BG10<br/>Mở rộng tương lai"]

    BR01["BR01<br/>Tự động tìm tài xế"]
    BR02["BR02<br/>Đặt xe"]
    BR03["BR03<br/>Quản lý nhận chuyến"]
    BR04["BR04<br/>Tìm tài xế thay thế"]
    BR05["BR05<br/>Theo dõi chuyến"]
    BR06["BR06<br/>Cập nhật trạng thái"]
    BR07["BR07<br/>Tính cước"]
    BR08["BR08<br/>Thanh toán"]
    BR09["BR09<br/>Thông báo"]
    BR10["BR10<br/>Quản lý vận hành"]
    BR11["BR11<br/>Báo cáo"]
    BR12["BR12<br/>Bảo mật & phân quyền"]
    BR13["BR13<br/>Khả năng mở rộng"]

    BP01["BP01<br/>Quản lý tài khoản"]
    BP02["BP02<br/>Đặt xe"]
    BP03["BP03<br/>Tìm & điều phối tài xế"]
    BP04["BP04<br/>Nhận / từ chối chuyến"]
    BP05["BP05<br/>Thực hiện & theo dõi chuyến"]
    BP06["BP06<br/>Tính cước & thanh toán"]
    BP07["BP07<br/>Gửi thông báo"]
    BP09["BP09<br/>Quản lý vận hành"]
    BP10["BP10<br/>Báo cáo & quản trị"]

    FR01["FR01<br/>Đăng ký"]
    FR02["FR02<br/>Đăng nhập"]
    FR03["FR03<br/>Thông tin cá nhân"]
    FR04["FR04<br/>Tạo yêu cầu đặt xe"]
    FR05["FR05<br/>Tìm tài xế phù hợp"]
    FR06["FR06<br/>Gửi yêu cầu tài xế"]
    FR07["FR07<br/>Nhận / từ chối"]
    FR08["FR08<br/>Tìm tài xế thay thế"]
    FR10["FR10<br/>Theo dõi trạng thái"]
    FR11["FR11<br/>Cập nhật trạng thái"]
    FR12["FR12<br/>Cập nhật vị trí"]
    FR13["FR13<br/>Tính cước"]
    FR14["FR14<br/>Thanh toán"]
    FR15["FR15<br/>Thanh toán thất bại"]
    FR16["FR16<br/>Gửi thông báo"]
    FR19["FR19<br/>Quản lý vận hành"]
    FR20["FR20<br/>Tra cứu giao dịch"]
    FR21["FR21<br/>Xử lý sự cố"]
    FR22["FR22<br/>Báo cáo"]
    FR23["FR23<br/>Phân quyền"]

    UC01["UC01<br/>Quản lý tài khoản"]
    UC02["UC02<br/>Đặt xe"]
    UC03["UC03<br/>Tìm & phân công tài xế"]
    UC04["UC04<br/>Nhận / từ chối chuyến"]
    UC05["UC05<br/>Thực hiện chuyến"]
    UC06["UC06<br/>Theo dõi chuyến"]
    UC07["UC07<br/>Tính cước"]
    UC08["UC08<br/>Thanh toán"]
    UC09["UC09<br/>Gửi thông báo"]
    UC12["UC12<br/>Quản lý vận hành"]
    UC13["UC13<br/>Xử lý sự cố"]
    UC14["UC14<br/>Tra cứu giao dịch"]
    UC15["UC15<br/>Xem báo cáo"]

    BG01 --> BR01
    BG01 --> BR03
    BG01 --> BR04

    BG02 --> BR07
    BG02 --> BR08

    BG03 --> BR02
    BG03 --> BR05
    BG03 --> BR06

    BG04 --> BR01
    BG05 --> BR10
    BG06 --> BR09
    BG07 --> BR11
    BG08 --> BR13
    BG09 --> BR12
    BG10 --> BR13

    BR01 --> BP03
    BR02 --> BP02
    BR03 --> BP04
    BR04 --> BP04
    BR05 --> BP05
    BR06 --> BP05
    BR07 --> BP06
    BR08 --> BP06
    BR09 --> BP07
    BR10 --> BP09
    BR11 --> BP10
    BR12 --> BP09
    BR13 --> BP10

    BP01 --> FR01
    BP01 --> FR02
    BP01 --> FR03

    BP02 --> FR04

    BP03 --> FR05
    BP03 --> FR06

    BP04 --> FR07
    BP04 --> FR08

    BP05 --> FR10
    BP05 --> FR11
    BP05 --> FR12

    BP06 --> FR13
    BP06 --> FR14
    BP06 --> FR15

    BP07 --> FR16

    BP09 --> FR19
    BP09 --> FR20
    BP09 --> FR21
    BP09 --> FR23

    BP10 --> FR22

    FR01 --> UC01
    FR02 --> UC01
    FR03 --> UC01
    FR04 --> UC02
    FR05 --> UC03
    FR06 --> UC03
    FR07 --> UC04
    FR08 --> UC04
    FR10 --> UC06
    FR11 --> UC05
    FR12 --> UC05
    FR13 --> UC07
    FR14 --> UC08
    FR15 --> UC08
    FR16 --> UC09
    FR19 --> UC12
    FR20 --> UC14
    FR21 --> UC13
    FR22 --> UC15
    FR23 --> UC12
```

# B13 – Acceptance Criteria (AC)

| **Mã AC** | **Acceptance Criteria** |
|:---:|---|
| **AC01** | Khách hàng có thể đăng ký, đăng nhập và cập nhật thông tin tài khoản thành công. |
| **AC02** | Khách hàng có thể nhập điểm đón, điểm đến, chọn loại xe và gửi yêu cầu đặt xe. |
| **AC03** | Hệ thống tự động tìm tài xế phù hợp dựa trên trạng thái sẵn sàng, vị trí và tiêu chí đã được doanh nghiệp xác nhận. |
| **AC04** | Khi tài xế từ chối hoặc không phản hồi, hệ thống tiếp tục tìm tài xế khác mà khách hàng không cần tạo lại yêu cầu. |
| **AC05** | Khi không tìm được tài xế, hệ thống phải thông báo rõ cho khách hàng. |
| **AC06** | Tài xế có thể nhận chuyến và hệ thống không tiếp tục phân công chuyến đó cho tài xế khác. |
| **AC07** | Tài xế có thể cập nhật đúng các trạng thái của chuyến theo trình tự hợp lệ. |
| **AC08** | Khách hàng có thể theo dõi trạng thái chuyến trong quá trình thực hiện. |
| **AC09** | Sau khi chuyến hoàn thành, hệ thống xác định được số tiền khách hàng phải trả theo chính sách doanh nghiệp. |
| **AC10** | Khách hàng có thể thanh toán bằng tiền mặt hoặc phương thức điện tử được hỗ trợ. |
| **AC11** | Khi thanh toán điện tử thất bại, hệ thống thông báo kết quả và cho phép xử lý lại theo chính sách doanh nghiệp. |
| **AC12** | Hệ thống gửi thông báo đến đúng khách hàng hoặc tài xế khi xảy ra các sự kiện quan trọng. |
| **AC13** | Khách hàng có thể xem lịch sử chuyến và đánh giá tài xế sau khi chuyến hoàn thành. |
| **AC14** | Nhân viên vận hành có thể quản lý khách hàng, tài xế, phương tiện và chuyến đi theo quyền được cấp. |
| **AC15** | Nhân viên vận hành có thể tra cứu giao dịch và hỗ trợ xử lý chuyến bị lỗi. |
| **AC16** | Ban lãnh đạo có thể xem báo cáo về số chuyến, doanh thu, tỷ lệ hoàn thành, tỷ lệ hủy và hiệu quả tài xế. |
| **AC17** | Người dùng không có quyền không thể thực hiện chức năng quản trị không được phép. |
| **AC18** | Các thao tác quản trị quan trọng được lưu vết để phục vụ kiểm tra. |


# B14 – Requirement Traceability Matrix (RTM)

| **BG** | **BR** | **FR**           | **UC** |   **AC**   |
| :----: | :----: | :--------------- | :----: | :--------: |
|  BG01  |  BR01  | FR05, FR06       |  UC03  |    AC03    |
|  BG01  |  BR03  | FR07             |  UC04  |    AC06    |
|  BG01  |  BR04  | FR08             |  UC04  |    AC04    |
|  BG02  |  BR07  | FR13             |  UC07  |    AC09    |
|  BG02  |  BR08  | FR14, FR15       |  UC08  | AC10, AC11 |
|  BG03  |  BR02  | FR04             |  UC02  |    AC02    |
|  BG03  |  BR05  | FR10             |  UC06  |    AC08    |
|  BG03  |  BR06  | FR11, FR12       |  UC05  |    AC07    |
|  BG04  |  BR01  | FR01, FR02, FR03 |  UC01  |    AC01    |
|  BG05  |  BR10  | FR19             |  UC12  |    AC14    |
|  BG05  |  BR10  | FR21             |  UC13  |    AC15    |
|  BG05  |  BR10  | FR20             |  UC14  |    AC15    |
|  BG06  |  BR09  | FR16             |  UC09  |    AC12    |
|  BG07  |  BR11  | FR22             |  UC15  |    AC16    |
|  BG09  |  BR12  | FR23             |  UC12  |    AC17    |
|  BG09  |  BR12  | —                |  UC12  |    AC18    |
|  BG10  |  BR13  | —                |    —   |      —     |

### Sơ đồ B14
```mermaid
flowchart LR

    BG01["BG01<br/>Tự động tìm & điều phối tài xế"]
    BG02["BG02<br/>Thanh toán"]
    BG03["BG03<br/>Quản lý & theo dõi chuyến"]
    BG04["BG04<br/>Quản lý tài khoản"]
    BG05["BG05<br/>Hỗ trợ vận hành"]
    BG06["BG06<br/>Thông báo"]
    BG07["BG07<br/>Báo cáo quản trị"]
    BG09["BG09<br/>Bảo mật"]
    BG10["BG10<br/>Mở rộng tương lai"]

    BR01["BR01<br/>Tự động tìm tài xế"]
    BR02["BR02<br/>Đặt xe"]
    BR03["BR03<br/>Quản lý nhận chuyến"]
    BR04["BR04<br/>Tìm tài xế thay thế"]
    BR05["BR05<br/>Theo dõi chuyến"]
    BR06["BR06<br/>Cập nhật trạng thái"]
    BR07["BR07<br/>Tính cước"]
    BR08["BR08<br/>Thanh toán"]
    BR09["BR09<br/>Thông báo"]
    BR10["BR10<br/>Quản lý vận hành"]
    BR11["BR11<br/>Báo cáo"]
    BR12["BR12<br/>Bảo mật & phân quyền"]
    BR13["BR13<br/>Khả năng mở rộng"]

    FR01["FR01<br/>Đăng ký"]
    FR02["FR02<br/>Đăng nhập"]
    FR03["FR03<br/>Thông tin cá nhân"]
    FR04["FR04<br/>Tạo yêu cầu đặt xe"]
    FR05["FR05<br/>Tìm tài xế phù hợp"]
    FR06["FR06<br/>Gửi yêu cầu tài xế"]
    FR07["FR07<br/>Nhận / từ chối"]
    FR08["FR08<br/>Tìm tài xế thay thế"]
    FR10["FR10<br/>Theo dõi trạng thái"]
    FR11["FR11<br/>Cập nhật trạng thái"]
    FR12["FR12<br/>Cập nhật vị trí"]
    FR13["FR13<br/>Tính cước"]
    FR14["FR14<br/>Thanh toán"]
    FR15["FR15<br/>Thanh toán thất bại"]
    FR16["FR16<br/>Gửi thông báo"]
    FR19["FR19<br/>Quản lý vận hành"]
    FR20["FR20<br/>Tra cứu giao dịch"]
    FR21["FR21<br/>Xử lý sự cố"]
    FR22["FR22<br/>Báo cáo"]
    FR23["FR23<br/>Phân quyền"]

    UC01["UC01<br/>Quản lý tài khoản"]
    UC02["UC02<br/>Đặt xe"]
    UC03["UC03<br/>Tìm & phân công tài xế"]
    UC04["UC04<br/>Nhận / từ chối chuyến"]
    UC05["UC05<br/>Thực hiện chuyến"]
    UC06["UC06<br/>Theo dõi chuyến"]
    UC07["UC07<br/>Tính cước"]
    UC08["UC08<br/>Thanh toán"]
    UC09["UC09<br/>Gửi thông báo"]
    UC12["UC12<br/>Quản lý vận hành"]
    UC13["UC13<br/>Xử lý sự cố"]
    UC14["UC14<br/>Tra cứu giao dịch"]
    UC15["UC15<br/>Xem báo cáo"]

    AC01["AC01"]
    AC02["AC02"]
    AC03["AC03"]
    AC04["AC04"]
    AC06["AC06"]
    AC07["AC07"]
    AC08["AC08"]
    AC09["AC09"]
    AC10["AC10"]
    AC11["AC11"]
    AC12["AC12"]
    AC14["AC14"]
    AC15["AC15"]
    AC16["AC16"]
    AC17["AC17"]
    AC18["AC18"]

    BG01 --> BR01
    BG01 --> BR03
    BG01 --> BR04

    BR01 --> FR05
    BR01 --> FR06
    BR03 --> FR07
    BR04 --> FR08

    FR05 --> UC03
    FR06 --> UC03
    FR07 --> UC04
    FR08 --> UC04

    UC03 --> AC03
    UC04 --> AC06
    UC04 --> AC04

    BG02 --> BR07
    BG02 --> BR08
    BR07 --> FR13
    BR08 --> FR14
    BR08 --> FR15
    FR13 --> UC07
    FR14 --> UC08
    FR15 --> UC08
    UC07 --> AC09
    UC08 --> AC10
    UC08 --> AC11

    BG03 --> BR02
    BG03 --> BR05
    BG03 --> BR06
    BR02 --> FR04
    BR05 --> FR10
    BR06 --> FR11
    BR06 --> FR12
    FR04 --> UC02
    FR10 --> UC06
    FR11 --> UC05
    FR12 --> UC05
    UC02 --> AC02
    UC06 --> AC08
    UC05 --> AC07

    BG04 --> BR01
    BR01 --> FR01
    BR01 --> FR02
    BR01 --> FR03
    FR01 --> UC01
    FR02 --> UC01
    FR03 --> UC01
    UC01 --> AC01

    BG05 --> BR10
    BR10 --> FR19
    BR10 --> FR20
    BR10 --> FR21
    FR19 --> UC12
    FR20 --> UC14
    FR21 --> UC13
    UC12 --> AC14
    UC14 --> AC15
    UC13 --> AC15

    BG06 --> BR09
    BR09 --> FR16
    FR16 --> UC09
    UC09 --> AC12

    BG07 --> BR11
    BR11 --> FR22
    FR22 --> UC15
    UC15 --> AC16

    BG09 --> BR12
    BR12 --> FR23
    FR23 --> UC12
    UC12 --> AC17
    BR12 --> AC18

    BG10 --> BR13
```

