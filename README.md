# 資料庫系統專案：學生、巴士與社交關係

本專案建立了一個完整的資料庫架構，包含學生、學校、巴士乘車記錄、寵物以及好友社交關係。

## 實體關係圖 (ERD)

# 資料庫系統專案：學生、巴士與社交關係

本專案建立了一個完整的資料庫架構，包含學生、學校、巴士乘車記錄、寵物以及好友社交關係。

## 實體關係圖 (ERD)

```# 資料庫系統專案：學生、巴士與社交關係

本專案建立了一個完整的資料庫架構，包含學生、學校、巴士乘車記錄、寵物以及好友社交關係。

## 實體關係圖 (ERD)

```mermaid
erDiagram
    SCHOOL ||--o{ STUDENT : "就讀"
    STUDENT ||--o{ PET : "擁有"
    STUDENT ||--o{ ride_record : "搭乘"
    BUS ||--o{ ride_record : "被搭乘"
    STUDENT ||--o{ good_friends : "好友社交"

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
        int capacity "載客量"
    }

    ride_record {
        int ride_id PK "紀錄ID"
        string student_id FK "學號"
        string plate_number FK "車牌號碼"
        datetime ride_time "搭乘時間"
    }

    PET {
        int pet_id PK "寵物ID"
        string pet_name "名字"
        string owner_id FK "主人學號"
    }

    good_friends {
        string student_id PK,FK "學生學號"
        string friend_name PK "好友姓名"
    }
```
