FROM node:18.15.0-bullseye-slim

# 作業ディレクトリを設定する
WORKDIR /src/front

# 依存関係をダウンロード
COPY ../../frontend/package*.json ./

# コピーした依存関係をダウンロード
RUN npm install