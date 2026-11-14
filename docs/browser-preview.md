# ブラウザプレビューの公開方法

## 現在の実装

- Webアプリ本体: `site/`
- トップページ: `site/index.html`
- 最初の学習ページ: `site/lesson-cubic.html`
- デプロイ設定: `.github/workflows/pages.yml`

GitHub Pages は静的な HTML / CSS / JavaScript を配信する。今回のプレビューはこの方式で動く。データベースやログイン機能はまだない。

## 重要：リポジトリがPrivateであること

現在の `BC-sileo/Math-OS` は Private。

GitHub公式仕様では、GitHub Free の個人アカウントで Pages を使えるのは Public リポジトリ。Private リポジトリから公開するには GitHub Pro / Team / Enterprise 等の対象プランが必要。さらに、Pagesで公開したサイトはインターネット上で誰でも閲覧できる。リポジトリ自体がPrivateでも、公開サイトはPrivateにはならない。

公式説明:
- https://docs.github.com/en/pages/getting-started-with-github-pages/what-is-github-pages
- https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site

## 設定手順（Privateのまま公開できるプランの場合）

1. GitHubで `BC-sileo/Math-OS` を開く。
2. **Settings** を開く。
3. 左側メニューの **Pages** を開く。
4. **Build and deployment** の **Source** を **GitHub Actions** にする。
5. `.github/workflows/pages.yml` が main ブランチにあることを確認する。
6. **Actions** タブで **Deploy Math-OS preview** の実行結果を確認する。
7. 成功後、Settings → Pages に表示される **Visit site** を押す。

通常のプロジェクトサイトURLは `https://BC-sileo.github.io/Math-OS/` の形式になる。実際のURLはGitHubのPages画面に表示されたものを使う。

## GitHub Free の場合（推奨）

PrivateリポジトリをPublicに変更する必要はない。元の `Math-OS` はPrivateのまま保ち、公開用に別のPublicリポジトリ（例: `Math-OS-preview`）を作り、`site/` の中身だけをそちらへ置く。

この分離なら、設計メモ・未公開の教材データ・開発中の内容を不用意に公開せず、ブラウザ表示用のファイルだけを公開できる。公開用リポジトリの作成とファイル配置は、公開に同意してから行う。

## 公開前チェック

- 公開サイトに個人情報・秘密情報・未公開にしたい内容が含まれていない。
- 公開されるファイルの範囲を確認した。
- 公開URLは誰でも見られることを理解している。
