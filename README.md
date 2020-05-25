
## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false, index: true|
|email|string|null: false, unique:true|
|password|string|null: false|

## Association
- has_many :groups, through : :groups_users
- has_many :groups_users
- has_many :messages

## groupsテーブル

|column|type|Options|
|------|----|-------|
|name|string|null: false|

## Association
- has_many :users, through : :groups_users
- has_many :messages
- has_many :groups_users

## messagesテーブル

|column|type|Options|
|------|----|-------|
|body|text||
|image|string||
|user|references|null: false, foreign_key: true|
|group|references|null: false, foreign_key: true|

## Association
- belongs_to :group
- belongs_to :user

## groups_usersテーブル

|column|type|Options|
|------|----|-------|
|user|references|null: false, foreign_key: true|
|group|references|null: false, foreign_key: true|

## Association
- belongs_to :group
- belongs_to :user