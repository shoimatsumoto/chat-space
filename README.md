# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...

### groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user


### usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|email|string|null:false|
|password|string|null:false|
### Association
- has_many :comments
- has_many :group
- has_many  :tags,  through:  :posts_tags


### commentsテーブル
|Column|Type|Options|
|------|----|-------|
|text|text|null: false|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :post
- belongs_to :user

### groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: fales|

### Association
- has_many :comments
- has_many :user
- has_many  :tags,  through:  :posts_tags
