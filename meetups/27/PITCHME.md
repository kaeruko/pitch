## Shinjuku mokumoku #27 成果

![](/images/lucky_yotsuba_clover_girl.png)

---

## 今日の目標

- 1.生徒さんのソースを読んで動作チェックする DONE!

- 2.勉強用にrailsのソースを読む

---

![](/images/disc.jpg)

おすすめされたプロジェクトのソースを落としてきて
bundle installしたところでエラー

```
(67 warnings and 3 errors generated.make: *** [generator.o] Error 1)
```

---

ローカル環境を変えたくなかったので

Dockerというものに入門して、その上でDiscourseを動かそうと思った。

---

Docker入門サイト見ながら
アプリケーションサーバ用のコンテナとDBサーバ用のコンテナを結合したところで認証プロトコルのエラー

```
ERROR 1251 (08004): Client does not support authentication protocol requested by server
```

アプリケーションサーバからmysqlサーバのmysqlに接続できない

---

dockerハブから取ってきたmysqlというdockerイメージのmysqlのバージョンは

```
Ver 8.0.13 for Linux on x86_64 (MySQL Community Server - GPL)
```

centos6にyumでインストールしたmysqlのバージョンは

```
mysql  Ver 14.14 Distrib 5.1.73, for redhat-linux-gnu (x86_64) using readline 5.1

```

---

コンテナ結合する意味あるかな？🤔
と思いアプリケーションサーバ単体でDiscourseを動かすことに
