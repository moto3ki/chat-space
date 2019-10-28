# chat-space DB設計
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|usename|string|null: false|
|email|string|null: false|
|password|string|null: false|
### Association
- has_many :comments
- has_many :chatgroups

## chatgroupsテーブル
|Column|Type|Options|
|------|----|-------|
|groupname|string|null: false|
|user_id|integer|null: false, foreign_key: true|
### Association
- has_many :users
- belongs_to :comment

## commentsテーブル
|Column|Type|Options|
|------|----|-------|
|text|text||
|image|text||
|user_id|integer|null: false, foreign_key: true|
|chatgroup_id|integer|null: false, foreign_key: true|
### Association
- has_many :users
- belongs_to :chatgroup

