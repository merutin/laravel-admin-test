# Laravel 10 + Laravel-Admin Test Project

このプロジェクトは、Laravel 10とlaravel-adminパッケージをセットアップしたテストプロジェクトです。

This project is a test setup of Laravel 10 with the laravel-admin package.

![Laravel-Admin Dashboard](https://github.com/user-attachments/assets/2b9b4a31-19c3-4559-bbc1-af8a1f1c0a49)

## 環境 / Environment

- PHP 8.1以上 / PHP 8.1 or higher
- Composer 2.x
- SQLite (デフォルトのデータベース / Default database)

## インストール / Installation

### 必要なパッケージのインストール / Install Dependencies

```bash
composer install
```

### 環境設定 / Environment Configuration

`.env.example`を`.env`にコピーして、アプリケーションキーを生成します。

Copy `.env.example` to `.env` and generate application key:

```bash
cp .env.example .env
php artisan key:generate
```

### データベースのセットアップ / Database Setup

SQLiteデータベースファイルを作成します。

Create SQLite database file:

```bash
touch database/database.sqlite
```

マイグレーションを実行します。

Run migrations:

```bash
php artisan migrate
```

### Laravel-Adminのセットアップ / Laravel-Admin Setup

Laravel-adminの初期データをシードします。

Seed the initial admin data:

```bash
php artisan db:seed --class=Encore\\Admin\\Auth\\Database\\AdminTablesSeeder
```

Laravel-adminのアセットをパブリッシュします。

Publish the laravel-admin assets:

```bash
php artisan vendor:publish --provider="Encore\Admin\AdminServiceProvider"
```

## 使用方法 / Usage

### 開発サーバーの起動 / Start Development Server

```bash
php artisan serve
```

### 管理画面へのアクセス / Access Admin Panel

ブラウザで以下のURLにアクセスしてください。

Open your browser and navigate to:

```
http://localhost:8000/admin
```

### デフォルトのログイン情報 / Default Login Credentials

- **ユーザー名 / Username**: `admin`
- **パスワード / Password**: `admin`

## インストール済みパッケージ / Installed Packages

- **Laravel Framework**: 10.49.1
- **Laravel-Admin**: 1.8.19

## テストの実行 / Running Tests

```bash
php artisan test
```

## セキュリティについて / Security Note

⚠️ **重要**: このプロジェクトはテスト/学習目的です。laravel-admin 1.8.19には既知のセキュリティ脆弱性(CVE-2023-24249)があります。本番環境での使用は推奨されません。

⚠️ **Important**: This project is for testing/learning purposes only. laravel-admin 1.8.19 has a known security vulnerability (CVE-2023-24249). It is not recommended for production use.

## Laravel-Adminについて / About Laravel-Admin

Laravel-adminは、Laravelフレームワーク用の管理パネルビルダーです。データベースのCRUD操作を簡単に行えるインターフェースを提供します。

Laravel-admin is an admin panel builder for Laravel framework. It provides an easy-to-use interface for database CRUD operations.

- [GitHub](https://github.com/z-song/laravel-admin)
- [Documentation](http://laravel-admin.org/docs)
- [Demo](http://laravel-admin.org/demo)
