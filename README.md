# ディレクトリ構成
```
app/
  ├ docker-compose.yml
  └ mysql
    └ Dockerfile
    └ my.cnf
  └ nginx
    └ default.conf
  └ php
    └ Dockerfile
    └ php.ini
```

# 以下Ubuntu22.04.3 LTSで動作確認

# Docker起動
sudo service docker start

# コンテナ起動
docker-compose up -d --build

# PHPコンテナに入る
docker-compose exec php bash

# nodeコンテナに入る
docker-compose exec node bash

npm run dev
(*エラー時 rm -rf node_modules rm package-lock.json)

# http確認
http://localhost:18888/

# DB
```
A5などのクライアントから接続する場合
mysql localhost:13306 root/root
pgsql localhost:15432 user/password
```

# MEMO
## コンテナ起動
$ docker-compose up -d

## コンテナ削除
$ docker-compose down

## コンテナ、イメージ、ボリューム、ネットワークを一括完全消去
$ docker-compose down --rmi all --volumes --remove-orphans

## phpコンテナに接続する（コンテナ名を変えて他のコンテナに接続できる）
$ docker-compose exec php bash

## Laravel install（最新版がsrc以下にインストールされる）
$ composer create-project laravel/laravel .

```バージョン指定する場合

Laravelの8.x系をインストールする
composer create-project laravel/laravel . "8.*"

Laravelの7.x系をインストールする
composer create-project laravel/laravel . "7.*"

Laravelの6.x系をインストールする
composer create-project laravel/laravel . "6.*"
```

## Laravel install後 パーミッション設定
$ chmod -R 777 storage/ bootstrap/cache/

## .env設定
$ vi .env

## migrate実行
$ php artisan migrate
