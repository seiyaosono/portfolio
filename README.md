# Portfolio

ポートフォリオ用の静的サイトです。現在はリポジトリと公開の基盤のみを用意し、デザイン・プロフィール・制作物は今後追加します。

- リポジトリ: <https://github.com/seiyaosono/portfolio>
- 公開URL: <https://seiyaosono.github.io/portfolio/>

## 構成

```text
site/
  index.html       # ページの内容（現在は準備中の表示のみ）
  styles.css       # 今後のデザインを追加
  script.js        # 今後の動作を追加
  .nojekyll        # 静的ファイルをそのまま配信
.github/workflows/
  deploy-pages.yml # main更新時に自動公開
```

HTML・CSS・JavaScriptの最小構成です。フレームワークや外部ライブラリのインストール、ビルドは不要です。

## 手元で確認する

このフォルダで次を実行します（Python 3が必要）。

```sh
python3 -m http.server 4173 --bind 127.0.0.1 --directory site
```

ブラウザーで <http://127.0.0.1:4173/> を開きます。終了は `Ctrl+C` です。

## GitHub Pages

公開対象は `site/` の中だけです。`main` へのpushでGitHub Actionsが公開します。リポジトリの **Settings → Pages → Build and deployment → Source** は **GitHub Actions** に設定します。

公開結果は **Actions → Deploy to GitHub Pages** で確認できます。**Run workflow** で手動公開もできます。

更新するときは、変更を確認してから必要なファイルをコミットしてpushします。

```sh
git status
git add site README.md .github/workflows/deploy-pages.yml .gitignore
git commit -m "Update portfolio"
git push origin main
```

## 今後の進め方

- デザインと構成は、要望が決まってから追加します。
- 画像などの公開素材は `site/` 内に置きます。
- CSS・JavaScript・画像のパスは `./styles.css` のような相対パスにします。
- APIキーやパスワードなどの秘密情報を置かないでください。ブラウザーに配信される内容は誰でも参照できます。

## 参考

- [GitHub Pagesの公開元の設定](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
- [GitHub Pagesのカスタムワークフロー](https://docs.github.com/en/pages/getting-started-with-github-pages/using-custom-workflows-with-github-pages)
