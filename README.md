# このリポジトリについて
[Swagger](https://swagger.io/)をDocker環境で動かしてみた

## 利用ツール

```sh
# 各バージョン
swagger-ui: v5.18.2
@redocly/cli: ^1.25.15
```

### Swagger

`OpenAPI`を利用し`REST API`を設計するために使用するツール。今回はその中でも[`Swagger UI`](https://swagger.io/tools/swagger-ui/)を利用。APIのドキュメントを書くために使う。

- [OpenAPI（ver3.0） のドキュメント](https://swagger.io/docs/specification/v3_0/about/)
- [Swagger UIのドキュメント](https://swagger.io/docs/open-source-tools/swagger-ui/usage/installation/)

### @redocly/cli

`Swagger UI`で作成したAPIドキュメントを、静的HTMLに生成するために使用。諸般の事情で、`@redocly/cli`が生成する静的HTMLと`Swagger UI`が作るAPIドキュメントの見た目が違うが、そういう仕様。

## ディレクトリ構成

```
.
├── README.md
├── docker-compose.yml
├── swagger
│   ├── openapi.yml
│   └── paths
└── redoc_cli
    ├── index.html
    ├── package-lock.json
    └── package.json
```

### `swagger`

 APIのドキュメントはここ
 
#### `openapi.yml`

API全体の概要を記載するドキュメント

#### `paths`

個々のAPIドキュメント（今後のAPI次第でさらにディレクトリ切るかも）
 
### `redoc_cli`

静的HTML生成のためのディレクトリ

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