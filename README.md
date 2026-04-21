# 🐘 My Laravel Infrastructure Template

自分専用の Laravel + Docker 開発スターターキットです。
PHP 8.3 / MySQL 8.0 / nginx / Node.js / phpMyAdmin がセットアップ済みです。

## 🛠 使い方 (セットアップ手順)

### 1. このテンプレートからリポジトリを作成
GitHub の "Use this template" ボタンから新しいリポジトリを作成してクローンします。

### 2. コンテナのビルドと起動
プロジェクトのルートで以下を実行します。
docker compose up -d --build

### 3. Laravel のインストール (新規作成の場合)
docker compose exec php composer create-project --prefer-dist laravel/laravel .

### 4. 権限の設定 (Permission denied 対策)
sudo chown -R $USER:$USER src
docker compose exec php chmod -R 777 storage bootstrap/cache

### 5. .env の設定
src/.env を開き、DB 接続情報を以下に書き換えます。
DB_HOST=mysql
DB_DATABASE=laravel_db
DB_USERNAME=laravel_user
DB_PASSWORD=laravel_pass

### 6. マイグレーション
docker compose exec php php artisan migrate


## 🔗 各ツールへのアクセス
Laravel: http://localhost
phpMyAdmin: http://localhost:8080
