
## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false, index: true|
|email|string|null: false, unique:true|
|password|string|null: false|

## Association
- has_many :groups_users
- has_many :groups
- has_many :messages

## groupsテーブル

|column|type|Options|
|------|----|-------|
|name|string|null: false|

## Association
has_many :users
- has_many :messages
- has_many :groups_users

## messagesテーブル

|column|type|Options|
|------|----|-------|
|body|text||
|image|string||
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

## Association
- belongs_to :group
- belongs_to :user

## groups_usersテーブル

|column|type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

## Association
- belongs_to :group
- belongs_to :user


