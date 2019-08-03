# Angularのサンプル

## プロジェクトの作成（マルチ構成）

### workspace作成

    npm i @angular/cli
    npx ng new my-apps --createApplication="false"
    rm -rf node_modules

### ライブラリ追加

1. yarn追加

        cd my-apps
        rm -rf node_modules
        npm i -D yarn
        rm -f package-lock.json

1. ライブラリの追加

        npx yarn add @angular/material @angular/cdk @angular/animations \
        handsontable @handsontable/angular

1. ライブラリのインストール

        npx yarn

### プロジェクト追加

    cd my-apps
    npx ng generate application sample-app

## アプリケーションの起動

1. 環境の起動  

        cd docker
        docker-compose up --build -d

1. アプリケーションの起動

        cd ../my-apps/
        npx ng serve sample-app

## デバッグ

1. アプリケーション起動
1. デバッグ設定（VSCodeの場合）

    launch.jsonに下記構成の追加（Chrome: Launch）

        {
            "type": "chrome",
            "request": "launch",
            "name": "Launch Chrome against localhost",
            "url": "http://localhost:4200",
            "webRoot": "${workspaceFolder}"
        }

1. ブレークポイント設定
1. <http://localhost:4200/>にアクセス

## アプリケーションの停止

1. アプリケーションの停止

    実行中のターミナル上で ^C

1. 環境の停止

        cd docker
        docker-compose stop && docker system prune -f
