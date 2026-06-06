# 退職後キャッシュフロー・シンプル試算 v8 PINロック版

GitHub Pagesで無料公開して、スマホのホーム画面に追加して使うためのPWA版です。

## ファイル構成

- `index.html`：シミュレーター本体
- `manifest.json`：スマホアプリ風表示の設定
- `sw.js`：オフラインキャッシュ用Service Worker
- `icon-192.png` / `icon-512.png`：PWAアイコン

## セキュリティ方針

- GitHub Pages公開を前提に、初期値に個人資産額は入れていません。
- 保存シナリオは、設定したPINから作る鍵で暗号化して、ブラウザのlocalStorageに保存します。
- PINは外部送信されません。
- PINを忘れると、保存シナリオは復元できません。
- CSV出力は暗号化されません。保存先の管理に注意してください。

## GitHub Pagesで公開する手順

1. GitHubで新しいリポジトリを作成する
2. このZIPを解凍して、中身をリポジトリ直下にアップロードする
3. GitHubのリポジトリ画面で `Settings` → `Pages` を開く
4. `Build and deployment` の `Source` を `Deploy from a branch` にする
5. `Branch` を `main`、フォルダを `/root` にして `Save`
6. 数分後に表示されるURLをスマホで開く
7. iPhoneならSafariの共有から「ホーム画面に追加」、AndroidならChromeのメニューから「ホーム画面に追加」または「アプリをインストール」

## 更新時の注意

`index.html` を差し替えた場合、スマホ側に古いキャッシュが残ることがあります。その場合は、ブラウザで再読み込みするか、ホーム画面アプリを一度削除して追加し直してください。
