SquirrelMail download filename patch
===========================

This code is fix to the garbled problem of the japanese file name for SquirrelMail.

* [SquirrelMail - Webmail for Nuts!](http://squirrelmail.org/)

SquirrelMail 1.4.22 で日本語ファイル名の文字化けに対応したコードとなります。
ベースとなるコードは、下記サイトにて提供されている"SquirrelMail Version 1.4.22 日本語設定PHP5.4対応版"となります。(差分をもとにししていただければ、他のコードにも適用可能と思います)
* [Webメールソフト SquirrelMail の PHP5.4対応 < サーバ管理 < taka2.info](http://taka2.info/20120705/squirrelmail-php54/)

対応としては、Content-Dispositonのfilenameを下記のような形式とするようにしています。
* IE(11未満)：UTF8でURLEncode
* 上記以外：RFC2231形式

確認ができているブラウザは下記の通りです。(全てWindowsです)
* IE7 (7.0.6002.18005)
* IE8 (8.0.7601.17514)
* IE9 (9.0.8112.16421)
* IE10 (10.0.9200.16721)
* IE11 (11.0.9600.17358)
* IE11 (11.0.9600.17358)※互換表示
* Firefox 33.0.2
* Chrome 38.0.2125.111 m
* Opera 25.0.1614.68

IE以外でRFC2231形式に対応していないもの(最近バージョンのものであれば、IE含めて対応していると思いますが)は、文字化けする可能性がありますので、ご注意ください。

Installation
------------

SquirrelMailをインストールしたディレクトリのfunctions配下の2ファイルを、本リポジトリで提供されているファイルと置き換えるだけです。
* functions/i18n.php
* functions/mime.php
