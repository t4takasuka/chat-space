# README

## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|email|string|null: false|
|group_id|integer|null: false|

### Association
- has_many :group, through: :user_group
- has_many :messages

## groupテーブル
|Column|Type|Options|
|------|----|-------|
|title|string|null: false|
|user_id|integer|null: false|

### Association
- has_many :users, through: :user_group
- has_many :messages

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|body|text|null: false|
|image|text||
|user_id|integer|null: false, foreing_key: true|
|group_id|integer|null: false, foreing_key: true|

### Association
- belong_to :user
- belong_to :group

## user_groupテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false|
|group_id|integer|null: false|

### Association
- belong_to :user
_ belong_to :group