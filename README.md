# テーブル設計

## usersテーブル

|   Column  | Type  | Option   |
|:---------:|:-----:|:--------:|
|email      |string |NOT NULL  |
|password   |string |NOT NULL  |
|name       |string |NOT NULL  |
|profile    |string |NOT NULL  |
|occupation |text   |NOT NULL  |
|position   |text   |NOT NULL  |

### Association

- has_many :comments
- has_many :prototypes


## prototypesテーブル

|   Column  | Type      | Option   |
|:---------:|:---------:|:--------:|
|title      |string     |NOT NULL  |
|catch_copy |text       |NOT NULL  |
|concept    |text       |NOT NULL  |
|user       |references |          |

### Association

- has_many :comments
- belongs_to :user


## commentsテーブル

|   Column  | Type      | Option   |
|:---------:|:---------:|:--------:|
|text       |text       |NOT NULL  |
|user       |references |NOT NULL  |
|prototype  |references |NOT NULL  |

### Association

- belongs_to :prototype
- belongs_to :user