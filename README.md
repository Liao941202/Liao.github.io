‵‵‵erDiagram
    SCHOOL ||--o{ STUDENT : "就讀 (1:N)"
    STUDENT }|--|{ BUS : "take_bus (N:M)"

    SCHOOL {
        string school_name PK "學校名稱"
        string place "地點"
    }

    STUDENT {
        string student_id PK "學號"
        string student_name "姓名"
        string major "系所"
        string school_name FK "所屬學校"
    }

    BUS {
        string plate_number PK "車牌號碼"
        string color "顏色"
        date buy_date "購買日期"
        int capacity "載客量"
    }

    take_bus {
        string student_id FK "學號"
        string plate_number FK "車牌號碼"
        int price "搭乘價格"
    }‵‵‵
