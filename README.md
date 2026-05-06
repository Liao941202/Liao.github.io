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
    STUDENT }|--|{ BUS : "搭乘 (ride_record)"
    STUDENT ||--o{ GOOD_FRIENDS : "社交 (好友名字連結)"

    SCHOOL {
        string school_name PK
        string place
    }

    STUDENT {
        string student_id PK
        string student_name
        string major
        string school_name FK
    }

    BUS {
        string plate_number PK
        string color
        int capacity
    }

    ride_record {
        int ride_id PK
        string student_id FK
        string plate_number FK
        datetime ride_time
    }

    PET {
        int pet_id PK
        string pet_name
        string owner_id FK
    }

    GOOD_FRIENDS {
        string student_id FK "學生學號"
        string friend_name "好友姓名"
    }
```
