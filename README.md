## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false, add_index|
|password|string|null: false, add_index|
|nickname|string|null: false, add_index|
### Association
- has_many :groups_users
- has_many :groups, through: :groups_users
- has_many :messages

## groupテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false, add_index|
|member|string|null: false|
### Association
- has_many :users, through: :groups_users
- has_many :messages

## messageテーブル
|Column|Type|Options|
|------|----|-------|
|contents|text|null: false|
|image|text||
### Association
- belongs_to :user
- belongs_to :group



