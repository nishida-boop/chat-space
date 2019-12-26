# chatspace DB設計
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|username|string|null: false|
### Association
- has_many :chatgroup
- has_many :comments

## chatgroupテーブル
|Column|Type|Options|
|------|----|-------|
|name|text|null: false|
|addition|text|null: false|
|user_id|integer|null: false, foreign_key: true|
｜username｜text|null: false|
### Association
- belongs_to :user
- has_many :comments

## commentsテーブル
|Column|Type|Options|
|------|----|-------|
|text|text|null: false|
|user_id|integer|null: false, foreign_key: true|
|chatgroup_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user
- has_many:chatgroup