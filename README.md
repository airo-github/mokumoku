# README

## 環境構築
```
$ bundle install --without=production
$ bin/rails db:setup
$ yarn install
$ bin/webpack
$ bin/rails s
```

## 事業をエンジニアリングしよう提案編の回答は以下に記述してください

### 選択した事業側の課題
サービス登録者数の内、男性60%に対して、女性は40%。
一方で、サービス内のもくもく会に参加した人の比率は、男性90%：女性10%と大きな差が出ています。
もっと女性が使いやすいようなサービス設計にする必要があるのではないか？

### 提案内容
ユーザー登録時に性別を入力するようにし、男性限定、女性限定開催のイベントを作成可能にする。
→ 現状ユーザーが男性か女性か判断することができないので女性の参加率の低下に繋がっていると考えられる。
  女性が安心して参加できるような仕組みを作る。

### 実装方針
- ユーザー登録時に性別入力できるようにする。ユーザーテーブルにgenderカラムを追加する。
- もくもく会の作成時にタグ指定できるようにし、男性限定、女性限定イベントは
  異性のイベントが表示されないようにする（異性が会場に現れる可能性があるため）
  問題点としてLGBTQの人をどう区別するかが課題である。
  肉体的性で区別するのが1番女性は安心すると思います。
- ヘッダーにある検索フォームにユーザーの性別限定イベントだけで検索できる。
  この時、チェックボックスを使用する。
- イベント作成時にオンライン、オフラインの場合は顔出しあり、顔出しなしを選択できるようにする。
  ヘッダーに開催条件の検索フォームを作成しチェックボックスで実装する。
  この時、チェックボックスを使用し複数選択可能にする。
- もくもく会一覧画面において、各画面に付与されているタグをタップするとそのタグで絞り込みが行われるようにする
