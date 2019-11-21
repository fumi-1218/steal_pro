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
|username|string|null: false|
|email|string|null: false|
|password|string|null: false|
### Association
- has_many :resaults
- has_many :total_results

## shopsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|emaal|string|null: false|
|password|string|null: false|
### Association
- has_many :results
- has_many :total_results

## user_shopsテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|references|null: false, foreign_key: true|
|shop_id|references|null: false, foreign_key: true|
### Association
- belongs_to :user
- belongs_to :shop

## resaultsテーブル
|Column|Type|Options|
|------|----|-------|
|number_of_match|integer|null: false|
|PPR|integer||
|try_double|integer||
|hit_double|integer||
|rating|integer|null: false|
|win_to_first|integer||
|win|integer|null: false|
|ton|integer||
|ton_eighty|integer||
|user_id|references|null: false, foreign_key: true|
|shop_id|references|null: false, foreign_key: true|
### Association
- has_many :total_resaluts
- belongs_to :user
- belongs_to :shop



## total_resalutsテーブル
|Column|Type|Options|
|------|----|-------|
|number_of_match|integer|null: false|
|PPR|integer||
|try_double|integer||
|hit_double|integer||
|rating|integer|null: false|
|win_to_first|integer||
|win|integer|null: false|
|ton|integer||
|ton_eighty|integer||
|user_id|references|null: false, foreign_key: true|
|shop_id|references|null: false, foreign_key: true|
### Association
- belongs_to :user
- belongs_to :result
- belongs_to :shop
