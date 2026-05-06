# 資料庫系統專案：學生、巴士與社交關係

本專案建立了一個完整的資料庫架構，包含學生、學校、巴士乘車記錄、寵物以及好友社交關係。

## 實體關係圖 (ERD)

```mermaid
erDiagram
    SCHOOL ||--o{ STUDENT : "就讀 (1:N)"
    STUDENT ||--o{ PET : "擁有 (1:N)"
    STUDENT }|--|{ BUS : "搭乘 (N:M via take_bus)"
    STUDENT ||--o{ GOOD_FRIENDS : "社交 (N:M)"

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
    }

    PET {
        int pet_id PK "寵物ID"
        string pet_name "名字"
        string owner_id FK "主人學號"
    }

    GOOD_FRIENDS {
        string student_id PK,FK "學生學號"
        string friend_id PK,FK "好友學號"
    }
```
