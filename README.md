## 概要
COACHTECH 教材 Tutorial 10-5「テスト ハンズオン演習」で作成した成果物です。
ユーザー登録機能を実装し、正常登録とメールアドレス重複時のバリデーションをフィーチャーテストで確認します。

## 使用技術
- PHP 8.1以上
- Laravel 10.x
- PHPUnit 10.x
- Eloquent ORM / Factory
- Laravel Sail（Docker環境）

## 学んだこと
- HTTPリクエストを使ったフィーチャーテストで、リダイレクトや認証状態を検証する。
- `RefreshDatabase` でテストごとにデータベースを初期化し、データベースの状態を確認する。
- バリデーションによるメールアドレス重複の検出と、セッションに返るエラーをテストする。

## 動作確認
Dockerを起動し、プロジェクトのルートディレクトリで実行します。初回のみ依存パッケージをインストールし、`.env` がない場合は作成します。

```bash
composer install
cp .env.example .env # .env がない場合のみ
```

`.env` の `DB_HOST` を `mysql` に設定します。

```bash
./vendor/bin/sail up -d
./vendor/bin/sail artisan key:generate # APP_KEY が未設定の場合のみ
./vendor/bin/sail artisan test
```
