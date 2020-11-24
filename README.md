## users

| Column          | Type   | Options     |
| --------------- | ------ | ----------- |
| nickname        | string | null: false |
| email           | string | null: false |
| password        | string | null: false |
| last_name       | string | null: false |
| first_name      | string | null: false |
| last_name_kana  | string | null: false |
| first_name_kana | string | null: false |
| birth_year      | string | null: false |
| birth_month     | string | null: false |
| birth_day       | string | null: false |

### Association
- has_many :items
- has_many :purchases


## items

| Column          | Type       | Options                        |
| --------------- | ---------- | ------------------------------ |
| image           |            |                                |
| nickname        | string     | null: false                    |
| name            | string     | null: false                    |
| text            | text       | null: false                    |
| category        | string     | null: false                    |
| condition       | string     | null: false                    |
| burden          | string     | null: false                    |
| area            | string     | null: false                    |
| day             | string     | null: false                    |
| price           | string     | null: false                    |
| user_id         | references | null: false, foreign_key: true |

### Association
- belongs_to :user
- has_one :purchase


## purchase

| Column          | Type       | Options                        |
| --------------- | ---------- | ------------------------------ |
| time            | string     | null: false                    |
| user_id         | references | null: false, foreign_key: true |
| item_id         | references | null: false, foreign_key: true |

- belongs_to :item
- has_one :address


## address

| Column          | Type       | Options                        |
| --------------- | ---------- | ------------------------------ |
| time            | string     | null: false                    |
| user_id         | references | null: false, foreign_key: true |
| item_id         | references | null: false, foreign_key: true |

