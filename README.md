# チャット機能と画像投稿機能のあるアプリです。
# ユーザー同志でグループを組むことができます。

# chatspace


# DB設計
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|nickname|string|null: false|
|email|string|null: false|
|password|string|null: false|
### Association
  has_many :coments
  has_many :users_groups
  has_many :groups through: :users_groups

## commentsテーブル
|Column|Type|Options|
|------|----|-------|
|text|text| |
|image|text| |
|user_id|integer|null: false, foreign_key: true|
### Association
  belongs_to :user
  belongs_to :guroup
  
## users_groups中間テーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
 belong_to :user
 belong_to :group

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
### Association
  has_many :coments
  has_many :users_groups
  has_many :users through: :users_groups
  





