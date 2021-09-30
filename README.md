# 初期設定としてデレクトリやファイルを作成して以下の様に配置をする。

```
  project (ルートディレクトリー)
  ├ docker-compose.yml
  ├ docker
  │  ├ php
  │  │  ├ php.ini
  │  │  └ Dockerfile
  │  └ nginx
  │     └ default.conf
  └ src (アプリのソースコードが入る)
```



# 環境構築の手順

1. ルートディレクトリへ移動, docker-compose.yml を基に各コンテナを作成し起動させる
  $ docker-compose up -d

2. phpコンテナ内に入る
  $ docker-compose exec php -bash

3. コンテナ内に入ったら,新規プロジェクト作成。(今回の場合だとアクセス時はコンテナ内のsrcディレクトリに居るので、そのディレクトリ直下にプロジェクトを作成するようにする)
  /src# composer create-project --prefer-dist laravel/laravel ./ "6.*"

4. 構築ができたので、ブラウザで localhost:80 でアクセスしてwelcomeページが表示されるか確認する。
