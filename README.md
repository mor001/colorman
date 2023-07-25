# 以下Ubuntu20.04で動作確認

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
localhost 13306 root/root

# MEMO
## コンテナ起動
$ docker-compose up -d

## コンテナ削除
$ docker-compose down

## コンテナ、イメージ、ボリューム、ネットワークを一括完全消去
$ docker-compose down --rmi all --volumes

## phpコンテナに接続する（コンテナ名を変えて他のコンテナに接続できる）
$ docker-compose exec php bash

## Laravel install
$ composer create-project laravel/laravel project-name

```バージョン指定
Laravelの8.x系をインストールする
composer create-project laravel/laravel project-name "8.*"

Laravelの7.x系をインストールする
composer create-project laravel/laravel project-name "7.*"

Laravelの6.x系をインストールする
composer create-project laravel/laravel project-name "6.*"
```

## Laravel install後 パーミッション設定
$ chmod -R 777 storage/ bootstrap/cache/