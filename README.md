# docker起動
$ docker-compose up -d

# .envコピー
$ cd server
$ cp .env.example .env


# phpコンテナに入ります
$ docker-compose exec php bash

# Laravelに関するライブラリをインストール
composer update --no-scripts

# 初期化
php artisan key:generate

# 確認
http://localhost

# DB接続
docker exec -it hr-db bash

# ログイン
mysql -u root -proot

# Tips
このエラーが出たとき

```
root@e22d671dc0ce:/var/www# php artisan migrate

   Illuminate\Database\QueryException 

  SQLSTATE[HY000] [1045] Access denied for user 'root'@'172.27.0.2' (using password: YES) (SQL: select * from information_schema.tables where table_schema = laravel and table_name = migrations and table_type = 'BASE TABLE')
```

```

docker exec -it hr-db bash

mysql -u root -proot

dbを作成して
create database test;

userを作成して
create user 'test'@'%' identified by 'testpass1234';

権限付与して
grant all on test.* TO 'test'@'%'
show grants for 'test'@'%';

.env編集して

docker-compose down
docker-compose up -d
docker-compose exec php bash
php artisan migrate

```