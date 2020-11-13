# テーブル設計

## users テーブル

| Column     | Type   | Options     |
| ---------- | ------ | ----------- |
| email      | string | null: false |
| password   | string | null: false |
| name       | string | null: false |
| profile    | text   | null: false |
| occupation | text   | null: false |
| position   | text   | null: false |

### Association

- has_many :prototype
- has_many :comments


## prototype テーブル

| Column     | Type       | Options     |
| ---------- | ---------- | ----------- |
| title      | string     | null: false |
| catch_copy | text       | null: false |
| user       | references |

### Association

- has_many :comments
- belongs_to :user

## comments テーブル

| Column    | Type       | Options      |
| --------- | ---------- | ------------ |
| text      | text       | null: falser |
| user      | references |              |
| prototype | references |              |

### Association

- belongs_to :user
- belongs_to :prototype
