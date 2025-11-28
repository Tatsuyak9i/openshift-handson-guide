# 親イメージ (base-app) を指定
# OpenShift内部のImageStreamを相対パスで参照
FROM base-app:latest
USER root
WORKDIR /deployments

# A. WARを展開 (ROOT.war -> ROOTディレクトリ)
# ※jarコマンドで展開し、元のWARは削除します
RUN mkdir ROOT && \
    cd ROOT && \
    jar -xf ../ROOT.war && \
    cd .. && \
    rm ROOT.war

# B. テナントごとの設定ファイルを注入
# (ビルドコンテキストにある application.yaml を展開済みディレクトリに配置)
COPY application.yaml /deployments/ROOT/WEB-INF/classes/application.yaml

# 権限を戻す
USER 185
