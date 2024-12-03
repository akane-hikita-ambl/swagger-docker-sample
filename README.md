# このリポジトリについて
[Swagger](https://swagger.io/)をDocker環境で動かしてみた

## 各バージョン

```sh
swagger-ui: v5.18.2
@redocly/cli: ^1.25.15
```

## コンテナ関連コマンド
### コンテナ作成

```sh
docker compose up -d
```

### コンテナ削除

```sh
docker compose down
```

### コンテナ起動/停止

【前提】コンテナ作成済み

```sh
docker compose start
docker compose stop
```


## 作成したAPI定義をブラウザで確認する

[http://localhost::8080](http://localhost:8080)にアクセス

## 作成したAPI定義書をHTMLファイルに出力する

`redoc_cli/index.html`というファイルが作成されます

### （初回のみ）インストール

```sh
cd redoc_cli
npm install
npm run html
```

### インストール済みの場合の実行コマンド

```sh
cd redoc_cli
npm run html
```