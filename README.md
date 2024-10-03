# テーブル設計

## users テーブル

| Column              | Type     | Options         |
| ------------------- | -------- | --------------- |
| email               | string   | null: false, unique: true |
| encrypted_password  | string   | null: false     |
| last_name           | string   | null: false     |
| first_name          | string   | null: false     |
| employee_num        | integer  | null: false     |

### Association

- has_many :works
- has_many :diaries

## works テーブル

| Column              | Type     | Options        |
| ------------------- | -------- | -------------- |
| customer            | string   | null: false    |
| task                | string   | null: false    |
| duration            | integer  | null: false    |
| charge              | integer  | null: false    |
| employee_num        | integer  | null: false    |
| model               | string   |                |
| location            | string   |                |
| user                | references | null: false, foreign_key: true |

### Association

- belongs_to :user
- has_many :diaries

## diaries テーブル

| Column              | Type     | Options        |
| ------------------- | -------- | -------------- |
| start               | integer  | null: false    |
| finish              | integer  | null: false    |

### Association

- belongs_to :user
- has_many :works