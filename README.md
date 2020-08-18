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