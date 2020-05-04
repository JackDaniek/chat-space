# README

## users table
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|index: true|
|email|string|null: false|unique: true|
|password|string|null: false|

### association
has_many :messages

has_many :groups_users

has_many :groups, through: :groups_users


## message table
|Column|Type|Options|
|------|----|-------|
|text|string|null: false|
|image|text|
|user_id|integer|foreign_key: true|
|group_id|integer|foreign_key: true|

### association
belongs_to :user

belongs_to :group


## groups table
|Column|Type|Options|
|------|----|-------|
|groupname|string|null: false|

### association
has_many :groups_users

has_many :users, through: :groups_users


## groups_uses table
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### association
belongs_to :user

belongs_to :group