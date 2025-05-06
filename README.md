# フラスコToDoアプリ

Flask + SQLite を使ったシンプルなToDoアプリです。タスクの作成・更新・削除・閲覧が可能です。

---

## 🔧 技術スタック

- Python 3.11
- Flask
- Flask-SQLAlchemy
- HTML / Bootstrap
- SQLite（ローカルDB）

---

## 💻 主な機能

- タスクの作成・編集・削除  
- 締切日を指定（過ぎると警告）  
- タスク詳細の表示  
- 日付順のソート表示  

---

## 🖥️ 実行環境

- **OS**：macOS Sonoma 15.1  
- **Python**：3.11.8  
- **主要パッケージ**：
  - Flask 2.2.5
  - Flask-SQLAlchemy 2.5.1
  - SQLite（ローカルDB使用）
- **その他のパッケージ**：`requirements.txt` を参照

---

## 📦 実行方法（ローカル環境）

```bash
git clone https://github.com/masaki43/flask-todo-app.git
cd flask-todo-app
pip install -r requirements.txt
python app.py
```

## 🚀 デプロイについて（Render使用）

### 試した手順

- GitHubリポジトリをRenderにインポート
- Build Command：`pip install -r requirements.txt`
- Start Command：`gunicorn app:app`
- 必要な環境変数や`wsgi.py`を用意し、Flaskアプリを起動

### 発生した問題

- SQLiteはローカルファイルベースのDBで、Renderの無料インスタンスではデータが永続化されない
- スリープ復帰後に`todo.db`が初期化され、タスクが消失する
- ポートバインディングエラーや不安定な動作も確認された

### 結論

無料プランでは安定した運用が難しいと判断し、今回は**ローカル実行形式で提出**しています。
