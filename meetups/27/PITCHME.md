## 12/22成果

![](/meetups/images/text_season_touji.png)

---

## 今日の目標

- 1.生徒さんのソースを読んで動作チェック ⭕️

- 2.勉強用にrailsのソースを読む

---

![](/meetups/images/disc.jpg)

おすすめされたプロジェクトのソース

(Discourse)を落としてきて

bundle installしたところでエラー

```
(67 warnings and 3 errors generated.make: *** [generator.o] Error 1)
```

---

🤔

ローカル環境を変えたくなかったので

Dockerというものに入門して

その上でDiscourseを動かそうと思った。

---

Docker入門サイト見ながら

アプリケーションサーバ用のコンテナと

DBサーバ用のコンテナを結合したところで

認証プロトコルのエラー

```
ERROR 1251 (08004): Client does not support authentication protocol requested by server
```

アプリケーションサーバからmysqlサーバの

mysqlに接続できない😭

---

mysqlコンテナのmysqlのバージョン

(dockerハブから取ってきた)


```
Ver 8.0.13 for Linux on x86_64 (MySQL Community Server - GPL)
```

アプリケーションコンテナのmysqlのバージョン

(centos6にyumでインストール)

```
mysql-5.1.73-8.el6_8.x86_64

```
---

・・・😑



コンテナ結合する意味あるかな？🤔
と思いアプリケーションサーバ単体でDiscourseを動かすことに
