* Ruby version
# chat-space DB設計
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|name|string|null: false|
### Association
- has_many :chat-space grupes
- has_many :comments
- belongs_to:chat-space grupes, through:  :authorizations

## chat-space grupesテーブル
|Column|Type|Options|
|------|----|-------|
|name|text|null: false|
|user_id|integer|null: false|
### Association
- belongs_to :user
- belongs_to:comments
- belongs_to:users,  through:  : authorizations

## authorizationsテーブル
|Column|Type|Options|
|------|----|-------|
|users_id|integer|null: false, foreign_key: true|
|chat-space grupes_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user
- belongs_to:chat-space grupes

## commentsテーブル
|Column|Type|Options|
|------|----|-------|
|text|text|null: false|
|image｜text||
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user
- belongs_to:chat-space grupes