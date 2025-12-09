# Laravel Lesson レビュー①

## Todo一覧機能

### Todoモデルのallメソッドで実行しているSQLは何か
SELECT * FROM Todos;
### Todoモデルのallメソッドの返り値は何か
Todoの情報が含まれるCollectionクラス
### 配列の代わりにCollectionクラスを使用するメリットは
配列と比べて、複雑な配列処理をシンプルなコードで実行できる。
### view関数の第1・第2引数の指定と何をしているか
第1引数：bladeファイルのパス、第2引数：bladeに渡す変数
### index.blade.phpの$todos・$todoに代入されているものは何か
$Todo:Todo全データ、$todo:$todosから1つずつ抜粋されたTodo
## Todo作成機能

### Requestクラスのallメソッドは何をしているか
viewの全ての入力値のnameとvalueを取得する
### fillメソッドは何をしているか
allメソッドで取得した全ての値をModelクラスのメンバーに代入する
### $fillableは何のために設定しているか
fillメソッドで代入できるメンバーを宣言するため
### saveメソッドで実行しているSQLは何か
INSERT INTO テーブル名(カラム名) VALUES (値);
### redirect()->route()は何をしているか
routeメソッドの引数に入力されたURIにリダイレクトさせる処理
## その他

### テーブル構成をマイグレーションファイルで管理するメリット
テーブル構成を開発メンバーで共有することができる
### マイグレーションファイルのup()、down()は何のコマンドを実行した時に呼び出されるのか
php artisan migrate, php artisan migrate:rollback
### Seederクラスの役割は何か
Seedingをする際のテストデータの定義
### route関数の引数・返り値・使用するメリット
引数: 名前付きルートの名前・実際の遷移先URL・Routingファイルから動的に取得することができるため、保守性が高い。
### @extends・@section・@yieldの関係性とbladeを分割するメリット
@extendsでベースのBladeファイルのパスを指定し、 ベースのBladeファイルに記載している@yieldと子ファイルの@sectionの引数の文字列が一致する箇所がマージされたHTMLファイルが生成される
メリット：全体レイアウトを分離することで全体レイアウトを変更した際の変更がベースBladeファイルのみとなり、保守性が向上する
### @csrfは何のための記述か
リクエストにCSRFトークンを付与するため
### {{ }}とは何の省略系か
<?= ~ > or <? echo ~>