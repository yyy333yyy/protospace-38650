#テーブル設計

## usersテーブル

| Column              | Type   | Options                       |
|-------------------- | ------ | ----------------------------- |
| email               | string | null: false, uniqueness: true |
| encrypted_password  | string | null: false                   |
| name                | string | null: false                   |
| profile             | text   | null: false                   |
| occupation          | text   | null: false                   |
| position            | text   | null: false                   |

### Association

- has_many :prototypes
- has_many :comments

## prototypesてーブル

| Column     | Type       | Options                        |
|----------- | ---------- |------------------------------- |
| title      | string     | null: false                    |
| catch_copy | text       | null: false                    |
| concept    | text       | null: false                    |
| user       | references | null: false, foreign_key: true |

### Association

- belongs_to :user
- has_many :comments


## commentsテーブル

| Column    | Type       | Opotions                       |
| --------- | ---------- | ------------------------------ |
| content   | text       | null: false                    |
| prototype | references | null: false, foreign_key: true |
| user      | references | null: false, foreign_key: true |

### Association

- belongs_to :user
- belongs_to :prototypes