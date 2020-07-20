# SWAGGER API MOCK

## これは何？
- Swagger(OpenAPI)でAPI定義を記述していくためのプロジェクト
- 主な構成は
  - Swagger Editor
  - Swagger UI(API定義のviewer1)
    - OpenAPI3で運用
  - Swagger API Mock(API モック)
    - [apisprout](https://github.com/danielgtaylor/apisprout)を利用
  - Redoc(API定義のviewer2)
- APIドキュメントファーストで開発したいときに

## 運用方針
- `swagger/openapi.yaml`にAPI定義を記述していく
- 都度viewerで確認していく
- フロントエンドの開発者はAPIモックを適宜利用してUI開発を進める

## 起動方法

    docker-compose up -d

## ブラウザからアクセスする

    # Swagger Editor
    http://127.0.0.1:9001

    # Swagger UI
    http://127.0.0.1:9002

    # Redoc
    http://127.0.0.1:9004

## API Mockにアクセスする場合のサンプル

    okazaki@okazakinoiMac swagger_api_mock % curl -i -X GET http://127.0.0.1:9003/pet/1 -H "accept: application/json"
    HTTP/1.1 200 OK
    Access-Control-Allow-Origin: *
    Content-Type: application/json
    Date: Mon, 20 Jul 2020 08:18:21 GMT
    Content-Length: 215

    {
    "category": {
        "id": 0,
        "name": "string"
    },
    "id": 0,
    "name": "doggie",
    "photoUrls": [
        "string"
    ],
    "status": "available",
    "tags": [
        {
        "id": 0,
        "name": "string"
        }
    ]
    }%

## 今後
- `openapi.yaml`を分割して運用していく仕組みを検討
