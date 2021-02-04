# README

DB設計について

料理の動画を簡単に検索、閲覧できるウェブアプリケーションを目指す

## usersテーブル

| Column                   | Type       | Options                   |
| ------------------------ | ---------- | ------------------------- |
| name                     | string     | null: false               |
| email                    | string     | null: false, unique: true |
| encrypted_password       | string     | null: false               |

### Association
- has_many :movies
- has_many :comments

## moviesテーブル

| Column           | Type       | Options                        |
| ---------------- | ---------- | ------------------------------ |
| name             | string     | null: false                    |
| explanation      | text       | null: false                    |
| category_id      | integer    | null: false                    |
| time_id          | integer    | null: false                    |
| user_id          | integer    | null: false, foreign_key: true |

### Association
- belongs_to :user
- has_many :comments

 ## commentsテーブル

| Column        | Type       | Options                        |
| ------------- | ---------- | ------------------------------ |
| text          | text       | null: false                    |
| user_id       | integer    | null: false, foreign_key: true |
| item_id       | integer    | null: false, foreign_key: true |

- belongs_to :user
- belongs_to :movie


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
