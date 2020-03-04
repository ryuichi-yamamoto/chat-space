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

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|username|string||null: false|
|email|string|null: false|
|password|string|null: false|
### Association
- belongs_to :group_users
- has_many :posts

## postsテーブル
|Column|Type|Options|
|------|----|-------|
|text|text|null: false|
|image|twxt||
|user_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :users
- belongs_to :groups_users

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|groupname|integer|null: false, foreign_key: true|
### Association
- has_many :posts
- has_many :groups_users


## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :groups
- belongs_to :users