# docker/Dockerfile

FROM python:3.10

# 作業ディレクトリ作成
WORKDIR /app

# wait-for-it.shをコンテナにコピー
COPY ./docker/wait-for-it.sh /wait-for-it.sh
RUN chmod +x /wait-for-it.sh

# 依存ファイルをコピー
COPY ../requirements.txt ./

# 必要なOSパッケージとPythonパッケージをインストール
RUN apt-get update && \
    apt-get install -y gcc libmariadb-dev && \
    pip install --upgrade pip && \
    pip install -r requirements.txt && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

# volume
EXPOSE 8000

