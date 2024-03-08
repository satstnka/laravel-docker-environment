# Docker を用いた Laravel 環境の構築
## 準備
### Homebrew のインストール
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

### PHP のインストール
```
brew install php
```

### composer のインストール
```
brew install composer
```

### node のインストール
```
brew install node
```

## プロジェクト作成
```
composer create-project --prefer-dist laravel/laravel [アプリケーション名]
```

### .env 編集
```
APP_NAME=[アプリケーション名]
APP_DEBUG=true
APP_KEY=

DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=[データベース名]
DB_USERNAME=[ユーザー名]
DB_PASSWORD=[パスワード]
DB_ROOT_PASSWORD=[rootパスワード]
```
- [アプリケーション名] はプロジェクト作成時のアプリケーション名に合わせる。
- [データベース名]、[ユーザー名], [パスワード], [rootパスワード] は任意に設定

### Docker コンテナ作成
```
docker-compose up -d
```

## プロジェクト作成後の開発作業
- 開発したアプリは http://localhost:8000/ で確認できる。
- DB の中身は http://localhost:8080/ で確認できる。
- Web アプリのコンテナには下記コマンドで入ることができる。
```
docker exec -it laravel-php /bin/bash
```

# 実行例
1. test という名前の Laravel プロジェクトを作成
```
composer create-project --prefer-dist laravel/laravel test
```

2. .env 編集
```
APP_NAME=test
APP_DEBUG=true
APP_KEY=

DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=test_db
DB_USERNAME=test_user
DB_PASSWORD=test_pass
DB_ROOT_PASSWORD=admin_pass
```

3. コンテナ作成
```
docker-compose up -d
```