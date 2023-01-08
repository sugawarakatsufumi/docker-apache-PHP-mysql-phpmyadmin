# docker-apache-PHP-mysql-phpmyadmin
docker php7.4+apache+mysql+phpmyadminの環境テンプレphp.ini、apache2設定変更も可能

## ファイル構成
- *./php_copy* にphp.iniのテンプレファイルがある
- *./apache_conf_copy* のsites-available/000-default.confがapacheの一般的なhttpd.confとにた働きをする
- *info.php* 動作テスト用
- *docker-compose.yml*

## 構築方法
docker-compose.ymlがあるディレクトリで`docker-compose up -d`を実行する
### phpの設定を変えられるにする方法
1. php_copyから*php.ini-production又はphp.ini-development*を*./docker/php*にコピー*php.ini*にリネーム 
1. これでphpの設定をいじれる様になります(変更した際には再起動を忘れないでください)

php.iniはこれを加えた方がよい
``` 
[Date]
date.timezone = "Asia/Tokyo"
[mbstring]
mbstring.internal_encoding = "UTF-8"
mbstring.language = "Japanese"
``` 

### httpd.confぽいことをしたい
1. apache_conf_copyから*sites-available/000-default.conf*を*./docker/sites-available*にコピー
1. これでapacheの設定を色々いじれる様になります(変更した際には再起動を忘れないでください)

## 参考
https://blog.nekozuki.me/nl30
https://qiita.com/snyt45/items/b54ce2ac5be2a474d9b6
https://qiita.com/sugurutakahashi12345/items/5daf89b2d33ef8d9fa2e

## コマンドメモ
`docker cp docker-apachephpmysqlphpmyadmin-php-1:/usr/local/etc/php test`
