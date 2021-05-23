# テーブル設計

## users テーブル

| Column                     | Type     | Options                   |
| -------------------------  | -------  | -----------------------   |
| name                       | string   | null: false               |
| encrypted_password         | string   | null: false               |
| email                      | string   | null: false, unique: true |
| birthday                   | date     | null: false               |
| family_name                | string   | null: false               |
| first_name                 | string   | null: false               |
| family_name_kana           | string   | null: false               |
| first_name_kana            | string   | null: false               |
| postcode                   | string   | null: false               |
| phone_number               | string   | null: false               |

### Association
- has_many :date
- has_many :messages

## dates テーブル
| Column                     | Type     | Options                   |
| -------------------------  | -------  | -----------------------   |
| fleetime                   | datetime | null: false               |
| prefecture_id              | integer  | null: false               |
| city                       | string   | null: false, unique: true |
| block                      | string   |  |

### Association
- belongs_to :user

## messages テーブル
| Column                     | Type     | Options                   |
| -------------------------  | -------  | -----------------------   |
| genres                     | integer  | null: false               |
| content                    | string   | null: false               |
| user                       | references   | null: false, unique: true |

### Association
- belongs_to :user



