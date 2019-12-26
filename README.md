* Ruby version
# chat-space DB設計
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|name|string|null: false|
### Association
- has_many:grupes through: :grupes_users
- has_many:comments

## grupesテーブル
|Column|Type|Options|
|------|----|-------|
|name|text|null: false|
### Association
- belongs_to :user
- has_many:comments 
- has_many:users,  through:  : grupes_users

## grupes_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|grupe_id|integer|null: false, foreign_key: true|
### Association
- belongs_to:user
- belongs_to:grupes

## commentsテーブル
|Column|Type|Options|
|------|----|-------|
|text|text|null: false|
|image｜text||
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to:user
- belongs_to:grupes