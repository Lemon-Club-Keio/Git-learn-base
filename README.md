# Git-Learn-base
Lemonの新入生教育用レポジトリ-git教育用


以下が参考になります。
https://www.youtube.com/watch?v=cOTBf8bHsXo

## 1. Gitとは？

**Git** は、ソフトウェアのバージョン管理を行うための分散型バージョン管理システムのことを指します。変更履歴を記録し、過去の状態に戻したり、複数人での開発をスムーズに行うことができます。開発では、前のバージョンに戻したい、といったことだったり、複数人で開発する際には、同じファイルを同時に変更するとファイル変更に矛盾が起きるため、これらを管理するツールが必要ということはイメージできると思います。

## 2. GitとGitHubの違い
GitとGitHubは、混同されがちですが、厳密には違います。以下が各々の違いです。

| 項目 | 説明 |
|------|------|
| **Git** | ローカルでバージョン管理を行うツール |
| **GitHub** | Gitのリポジトリをホスティングするサービス（リモートリポジトリを管理する場所） |

Gitはローカルで使うものですが、GitHubを使うことでリモートリポジトリを管理し、複数人での開発が可能になります。複数マシンで開発を進めたいとき、複数人で開発を進め痛い時などにはgithubを利用しましょう。

---

## 3. Gitの基本操作（ハンズオン）
それでは、実際にgitを操作して、Gitに慣れてみましょう。百聞は一見に如かず。やっていけばなれます。

### 3.0. GitHubと通信できるように設定
Githubと通信するには、公開鍵暗号での認証が必要です。以下を参照しつつ一緒にやってみよう。
https://qiita.com/shizuma/items/2b2f873a0034839e47ce


### 3.1. Gitの初期設定（最初に一度だけ）
シェルを起動してください。ターミナルのこと。

```sh
# ユーザー名とメールアドレスの設定
git config --global user.name "あなたの名前"
git config --global user.email "あなたのメールアドレス"
```

### 3.2. リポジトリをクローンする
```sh
git clone https://github.com/your-repository/git-learn-base.git
cd git-learn-base
```

### 3.3. ブランチを作成する
```sh
# ブランチを作成し、そのブランチに切り替える
git checkout -b feature/new-feature
```

### 3.4. ファイルを編集して変更を確認する
```sh
# 変更の確認
git status
```

### 3.5. ファイルをステージングする
```sh
# 特定のファイルをステージングする
git add ファイル名

# curent directoryの変更をすべてステージングする
git add .
```

### 3.6. コミットする
```sh
git commit -m "[add] 新しい機能を追加"
```

### 3.7. リモートリポジトリにプッシュする
```sh
git push origin feature/new-feature
```

### 3.8. プルリクエスト（PR）を作成する
GitHubのWeb UIから「Pull Request」を作成し、レビューを依頼します。

---

## 4. ブランチとは？

ブランチとは、開発を並行して進めるための仕組みです。一般的に、以下のようなブランチ運用が行われます。

| ブランチ名 | 用途 |
|------------|------|
| **main (master)** | 本番環境の安定版コードを管理する |
| **develop** | 開発中のコードを統合する |
| **feature/** | 新機能の開発用ブランチ |
| **bugfix/** | バグ修正用ブランチ |

ブランチを適切に分けることで、開発をスムーズに進めることができます。

---

## 5. よく使うGitコマンド一覧

| コマンド | 説明 |
|----------|------|
| `git clone URL` | リモートリポジトリをローカルにコピーする |
| `git checkout -b ブランチ名` | 新しいブランチを作成して切り替える |
| `git add ファイル名` | 変更をステージングする |
| `git commit -m "メッセージ"` | コミットを作成する |
| `git push origin ブランチ名` | 変更をリモートリポジトリにプッシュする |
| `git pull origin ブランチ名` | リモートの変更をローカルに反映する |
| `git merge ブランチ名` | 指定したブランチを現在のブランチにマージする |
| `git branch -d ブランチ名` | ブランチを削除する |

---

## 6. まとめ

- **Git** はバージョン管理のためのツールであり、**GitHub** はリモートリポジトリをホスティングするサービス
- ブランチを活用することで、安全に機能開発やバグ修正ができる
- 基本的なコマンドを覚えて、スムーズにチーム開発を進めよう！

---
## 7. 発展
機密情報や、共有しておく必要のないものは、`.gitignore`fileに記述して、gitの管理対象から外すべきです。調べてみてください。

## 8. 参考リンク
- [Git公式ドキュメント](https://git-scm.com/doc)
- [GitHub Docs](https://docs.github.com/)

## 9. 課題
このレポジトリに`feat/your_family_name`という、ブランチを作成して、以下の中身を記述したtxtfileをgithubにpushしてください。Pull Requestを作って先輩に確認してもらってください。

```txt
hello github
```

*ヒント*
```console
git checkout -b feat/lemon
git add sample.txt
git commit -m "[add] sample.txt"
git push orifin feat/lemon
```
