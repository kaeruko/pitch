<style>
.markdown-body { font-size: 3px; }
</style>


## もくもく2/9成果

<img src="/meetups/images/snow.png" width="250">

@yokina

- プログラミングスクール講師やってます(laravel,rails)

- 最近ジムに通い始めました。

- 今週からスマートロックのrailsプロジェクトに参加。

---

## 💎RubyMine入れた💎

長年Sublime textだったけどリーダーがRubyMine派だったので入れてみた。

まだわからないけどクラス検索が便利。

あとSublime textよりgo to declarationが正確っぽい

---

## tig入れた

以前三木さんが使ってるの見て便利そうだったのでtig入れてみた。

gitのグラフがSourceTreeと違うので戸惑うけど

(tigはmasterブランチの最新が一番上に来るっぽい)

(SourceTreeはローカルに落としたすべてのリポジトリの最新順)

パスとファイル名のコピーが出来るの便利なのでしばらく並行して使ってみる。

---


## スマートロックのプロジェクトを読む

- 昨夜こっそり対応中だったissueがプロジェクトリーダーに対応されてしまったのでどうやって対応したのか差分を確認

操作ログテーブルに「ログインした」「新規登録した」「招待した」などのメッセージがstring型で入っていたのを

UserIdやメールアドレスなどの詳細情報をjsonbのカラムに変更して保存出来るようにする対応。


- 自分だったら何も考えずにjsonにして突っ込んじゃうところをちゃんと別のクラスにして管理してるのを見て
クソコードしか書けない自分が開発するの怖くなった😰

- ActiveRecordのjoins,mergeを覚えた

- 動作確認しない代わりにテスト駆動開発というのをやっているのでrspecからデバッグ文出して何が変わったのかを見た

---

PITCH.mdを先に作って、それに沿って作業してみた。

---

「人が対応したissueの差分を読む」という~~眠い~~気力のいる作業をやれたのは

shinjuku-mokumokuの緊張感ならでは☺️⚡️⚡️

---

<img src="/meetups/images/disc.jpg" width="300">

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
