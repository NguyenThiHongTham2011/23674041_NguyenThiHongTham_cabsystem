

## B1 – Ngữ cảnh nghiệp vụ và vấn đề nghiệp vụ

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

Đây là sơ đồ quan trọng nhất của B9:

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

## Bộ này bạn nên giữ làm “xương sống” của dự án

Quan trọng nhất là **không sửa mã lung tung** về sau:

**B1:** Context + Problem
**B2:** Stakeholder
**B3:** BG01–BG10
**B4:** Scope
**B5:** BR01–BR13
**B6:** BP01–BP10
**B7:** FR01–FR23
**B8:** BRU01–BRU13 + EX01–EX07
**B9:** Entity + ERD
**B10:** NFR01–NFR10
**B11:** UC01–UC15

b12 truy xuat nguon goc yeu cau
Đúng. **B12 – Truy xuất nguồn gốc yêu cầu (Requirement Traceability)** là bước để chứng minh rằng **mỗi yêu cầu đều xuất phát từ đâu và được triển khai xuống đâu**.

Với dự án CAB, để sau này làm Test Case không bị quá tải, mình khuyên **không truy xuất từng câu chữ**, mà nối theo chuỗi:

**Business Goal → Business Requirement → Business Process → Functional Requirement → Business Rule → Use Case → Test Case**

---

# B12 – Requirement Traceability

## 1. Ma trận truy xuất nguồn gốc yêu cầu

| BG   | BR               | BP         | FR                     | BRU / EX                  | UC               |
| ---- | ---------------- | ---------- | ---------------------- | ------------------------- | ---------------- |
| BG01 | BR01             | BP03       | FR05, FR06             | BRU01, BRU02              | UC03             |
| BG01 | BR03, BR04       | BP04       | FR07, FR08             | BRU03, BRU04, BRU05       | UC04             |
| BG02 | BR07, BR08       | BP06       | FR13, FR14, FR15       | BRU08, BRU09, BRU10, EX04 | UC07, UC08       |
| BG03 | BR02, BR05, BR06 | BP02, BP05 | FR04, FR10, FR11, FR12 | BRU07, EX05               | UC02, UC05, UC06 |
| BG04 | BR04             | BP01       | FR01, FR02, FR03       | BRU12, EX07               | UC01             |
| BG05 | BR10             | BP09       | FR19, FR21             | EX06, EX07                | UC12, UC13       |
| BG06 | BR09             | BP07       | FR16                   | —                         | UC09             |
| BG07 | BR11             | BP10       | FR22                   | —                         | UC15             |
| BG08 | BR13             | BP10       | —                      | —                         | —                |
| BG09 | BR12             | BP09       | FR23                   | BRU10, BRU12, BRU13       | UC12             |
| BG10 | BR13             | BP10       | —                      | —                         | —                |

### Ý nghĩa

Ví dụ:

**BG01 – Tự động tìm và điều phối tài xế**

↓

**BR01 – Tự động tìm tài xế**

↓

**BP03 – Tìm và điều phối tài xế**

↓

**FR05 – Tìm tài xế phù hợp**
**FR06 – Gửi yêu cầu đến tài xế**

↓

**BRU01 – Tài xế phải sẵn sàng**
**BRU02 – Ưu tiên tài xế phù hợp**

↓

**UC03 – Tìm và phân công tài xế**

Sau này từ **UC03** mới thiết kế Test Case.

---

# 2. Sơ đồ Traceability bằng Mermaid

Bạn có thể copy đoạn này vào Mermaid:

```mermaid
flowchart LR

    %% =========================
    %% BUSINESS GOALS
    %% =========================

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

    %% =========================
    %% BUSINESS REQUIREMENTS
    %% =========================

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

    %% =========================
    %% BUSINESS PROCESS
    %% =========================

    BP01["BP01<br/>Quản lý tài khoản"]
    BP02["BP02<br/>Đặt xe"]
    BP03["BP03<br/>Tìm & điều phối tài xế"]
    BP04["BP04<br/>Nhận / từ chối chuyến"]
    BP05["BP05<br/>Thực hiện & theo dõi chuyến"]
    BP06["BP06<br/>Tính cước & thanh toán"]
    BP07["BP07<br/>Gửi thông báo"]
    BP08["BP08<br/>Đánh giá"]
    BP09["BP09<br/>Quản lý vận hành"]
    BP10["BP10<br/>Báo cáo & quản trị"]

    %% =========================
    %% FUNCTIONAL REQUIREMENTS
    %% =========================

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
    FR21["FR21<br/>Xử lý sự cố"]
    FR22["FR22<br/>Báo cáo"]
    FR23["FR23<br/>Phân quyền"]

    FR01["FR01<br/>Đăng ký"]
    FR02["FR02<br/>Đăng nhập"]
    FR03["FR03<br/>Thông tin cá nhân"]

    %% =========================
    %% USE CASE
    %% =========================

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
    UC15["UC15<br/>Xem báo cáo"]

    %% =========================
    %% TRACEABILITY
    %% =========================

    BG01 --> BR01
    BG01 --> BR03
    BG01 --> BR04

    BG02 --> BR07
    BG02 --> BR08

    BG03 --> BR02
    BG03 --> BR05
    BG03 --> BR06

    BG04 --> BR04

    BG05 --> BR10

    BG06 --> BR09

    BG07 --> BR11

    BG08 --> BR13
    BG09 --> BR12
    BG10 --> BR13

    BR01 --> BP03
    BR03 --> BP04
    BR04 --> BP04
    BR02 --> BP02
    BR05 --> BP05
    BR06 --> BP05
    BR07 --> BP06
    BR08 --> BP06
    BR09 --> BP07
    BR10 --> BP09
    BR11 --> BP10
    BR12 --> BP09
    BR13 --> BP10

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
    FR21 --> UC13
    FR22 --> UC15
    FR23 --> UC12
```

---

## 3. Tại sao B12 rất quan trọng cho Test Case?

B12 giúp mình **không phải nghĩ Test Case từ đầu**.

Ví dụ chỉ cần nhìn:

> **BG01 → BR01 → BP03 → FR05 → UC03**

thì biết ngay phải kiểm thử chức năng:

**“Hệ thống có tìm được tài xế phù hợp hay không?”**

Sau đó mới sinh các Test Case:

* Tài xế đang sẵn sàng → tìm được.
* Tài xế không sẵn sàng → không được chọn.
* Có nhiều tài xế → chọn theo tiêu chí đã xác nhận.
* Tài xế từ chối → tìm tài xế khác.
* Không còn tài xế → thông báo khách hàng.

Như vậy **B12 chính là cây cầu nối từ yêu cầu của khách hàng → chức năng hệ thống → Use Case → Test Case**.

Và với dự án của bạn, mình sẽ **không tạo Test Case cho toàn bộ 23 FR một cách máy móc**; sẽ gom theo các **Use Case/luồng nghiệp vụ chính** để một người vẫn làm được.

