# rails-react
RailsAPI+React構成をつくってみたかった

## 起動
`docker-compose up -d`

`localhost:8000` => React

`localhost:3000` => Rails

### RailsAPIのコンテナにログイン 
`docker-compose exec api bash`

## 初回の環境構築メモ
```sh
docker-compose run api rails new . --force --no-deps --database=postgresql --api
docker-compose build

# React + TypeScript
docker-compose run --rm front sh -c "npm install -g create-react-app && create-react-app react-app --typescript"

# database.ymlを修正した後に実行
docker-compose up -d 
```
