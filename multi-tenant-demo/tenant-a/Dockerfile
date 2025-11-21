# 親イメージ (base-app) を指定
# OpenShift内部のImageStreamを相対パスで参照
FROM base-app:latest

# 顧客固有の設定ファイルを Tomcat のクラスパス配下にコピー
COPY application.yml /opt/jws-5.7/tomcat/webapps/ROOT/WEB-INF/classes/application.yml
