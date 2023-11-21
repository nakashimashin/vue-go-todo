# alpineを使ってDockerイメージを軽量化する
FROM golang:1.20.2-alpine

# Alpine Linuxにはgitが含まれていないため、gitをインストールする
RUN apk update && apk add git

# 作業ディレクトリを設定する
WORKDIR /src/back

# go.mod、go.sumをDockerコンテナ内にコピー
COPY ../../go.mod ./
COPY ../../go.sum ./

# コピーした依存関係をダウンロード
RUN go mod download