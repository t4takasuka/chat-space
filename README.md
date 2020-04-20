# README

## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|email|string|null: false|
|password|string|null: false|

### Association
- has_many :groups, through: :user_groups
- has_many :user_groups
- has_many :messages

## groupテーブル
|Column|Type|Options|
|------|----|-------|
|title|string|null: false|

### Association
- has_many :users, through: :user_groups
- has_many :user_groups
- has_many :messages

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|body|text||
|image|string||
|user_id|integer|null: false, foreing_key: true|
|group_id|integer|null: false, foreing_key: true|

### Association
- belong_to :user
- belong_to :group

## user_groupsテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false|
|group_id|integer|null: false|

### Association
- belong_to :user
- belong_to :group