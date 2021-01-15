# ProtoSpaceのER図



| users テーブル                  |  
| ---                            |  
| email (string型, NOT NULL)     |  
| password (string型, NOT NULL)  |  
| name (string型, NOT NULL)      |  
| profile (text型, NOT NULL)     |  
| occupation (text型, NOT NULL)  |  
| position (text型, NOT NULL)    |  

### Association

- has_many :comments
- has_many :prototypes


| comments テーブル               |  
| ---                            |  
| text (text型, NOT NULL)        |  
| user (references型)            |  
| prototype (references型)       |  

### Association

- belongs_to :user
- belongs_to :prototype


| prototypes テーブル             |  
| ---                            |  
| title (string型, NOT NULL)     |  
| catch_copy (text型, NOT NULL)  |  
| concept (text型, NOT NULL)     |  
| image (ActivesStorage型で実装)  |  
| user (references型)            |  

### Association

- belongs_to :user
- has_many :comments