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