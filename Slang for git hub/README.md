# スラング動画ノート PWA テスト版

スマホのホーム画面に追加でき、一度開けばオフラインでも動画ごと使えるようにした版です。
元のアプリ（/mnt/project-files/slang-clip-note/）の No.1〜No.4 の動画と、No.3・No.4 の行ごとの再生区間を組み込んであります。

## 中身
| ファイル | 内容 |
|---|---|
| index.html | アプリ本体 |
| manifest.webmanifest | アプリ名・アイコン・色の設定 |
| sw.js | オフラインで開けるようにする仕組み（動画もスマホに保存） |
| icons/ | ホーム画面用アイコン |
| videos/ | No.1〜No.4 の動画 |
| .nojekyll | GitHub Pages 用（中身は空でOK） |

## GitHub Pages で公開する手順
1. GitHub にログインし、右上の「＋」→「New repository」。名前は例えば `slang-clip-note`、**Public** を選んで作成。
2. 作成した画面の「uploading an existing file」を押し、このフォルダの中身（index.html・manifest.webmanifest・sw.js・icons フォルダ・videos フォルダ）をまとめてドラッグして「Commit changes」。
3. リポジトリの「Settings」→ 左の「Pages」→「Branch」を `main`・`/(root)` にして「Save」。
4. 1〜2分後、`https://（ユーザー名）.github.io/slang-clip-note/` で開けます。このURLを使う人に送るだけで、使う人は GitHub 不要です。

## スマホに入れる
- iPhone（Safari）：共有ボタン →「ホーム画面に追加」
- Android（Chrome）：メニュー →「アプリをインストール」または「ホーム画面に追加」

## 中身を更新するとき
ファイルを差し替えたら、sw.js の 1行目付近 `const VERSION = "v1";` を `"v2"` のように変えてアップロードします。そうしないとスマホ側に古い版が残ることがあります。
動画を追加したときは、sw.js の FILES の一覧と index.html の該当フレーズの `video:` にもファイル名を足します（Claude に頼めばまとめて直します）。

## このテスト版でできないこと
- アプリ内からの動画登録・差し替えはできません（元のアプリの機能）。動画の追加は上の更新手順で行います。
