# PHP App ① レビュー

## 全般

### 以下のaタグのリンクを押下した際にedit.phpの$_GETにどんな値が格納されるか説明してください。

```html
<a href="edit.php?todo_id=123&todo_content=焼肉">更新</a>
```
edit.phpがないので不明

### 以下のフォームの送信ボタンを押下した際にstore.phpの$_POSTにどんな値が格納されるか説明してください。

```html
<form action="store.php" method="post">
    <input type="text" name="id" value="123">
		<textarea　name="content">焼肉</textarea>
    <button type="submit">送信</button>
</form>
```
登録時の順番と入力内容で構成された連想配列が格納されます。
（キーは登録id バリューが123）

### `require_once()` は何のために記述しているか説明してください。
（）内に記載されたファイルを読み込み実行するため

### `savePostedData($post)`は何をしているか説明してください。
savePostedData($post)の記述無し

### `header('location: ./index.php')`は何をしているか説明してください。
header関数の前に記述した実装を記載されているファイルからデータを受け取り実行する

### `getRefererPath()`は何をしているか説明してください。
getRefererPath()の記述なし

### `connectPdo()` の返り値は何か、またこの記述は何をするための記述か説明してください。
config.phpに記載されているMySQLへの接続に必要なデータ（DSN, DB_USER, DB_PASSWORD）

### `try catch`とは何か説明してください。
throwで投げられた例外の内容を、tryのブロックで囲ったcatchブロックで受取りcatchブロック内に記述した例外処理を実行します。

### Pdoクラスをインスタンス化する際に`try catch`が必要な理由を説明してください。
サーバーが止まっている際にそれを知らせるため例外処理を行っています。

## 新規作成

### `createTodoData($post)`は何をしているか説明してください。
フォームに入力された内容をデータベースに登録するため値をデータベースと接続しているファイルに渡しています。

## 一覧

### `getTodoList()`の返り値について説明してください。
データベースにあるDELETEされていないすべてのデータ

### `<?= ?>`は何の省略形か説明してください。
<?php echo ; ?>の省略です

## 更新

### `getSelectedTodo($_GET['id'])`の返り値は何か、またなぜ`$_GET['id']` を引数に渡すのか説明してください。
getSelectedTodo($_GET['id'])の記述無し

### `updateTodoData($post)`は何をしているか説明してください。
updateTodoData($post)の記述無し

## 削除

### `deleteTodoData($id)`は何をしているか説明してください。
deleteTodoData($id)の記述無し

### `deleted_at`を現在時刻で更新すると一覧画面からToDoが非表示になる理由を説明してください。
deleted_atの記述無し

### 今回のように実際のデータを削除せずに非表示にすることで削除されたように扱うことを〇〇削除というか。
倫理削除

### 実際にデータを削除することを〇〇削除というか。
物理削除

### 前問のそれぞれの削除のメリット・デメリットについて説明してください。
倫理削除は後から値を取り戻すことが可能だが、物理削除はデータベースから完全に削除するため要注意