# 感性Wiki Lite / スマホ用Public版

スマホから使うための、公開用の軽量版です。

## 方針

- 個人的な初期メモは入れていません。
- 保存先はスマホのブラウザ内 `localStorage` です。
- Service Workerでアプリ本体をキャッシュするため、GitHub Pages（例: `three-box-task`）で初回読み込みした後はオフラインでも開けます。
- PC版・Private版とは自動同期しません。
- 必要なときだけCSVエクスポートして、Private側の保管庫へ反映します。

## 使い方

1. `index.html` を開く。
2. 初回だけオンラインでGitHub Pages上のページ（例: `https://<ユーザー名>.github.io/three-box-task/`）を開く。
3. スマホのブラウザで「ホーム画面に追加」する。
4. メモを追加・編集する。
5. 以後は圏外や機内モードでも、ホーム画面のアイコンから開いて使う。
6. 必要に応じてCSVエクスポートする。

## 注意

Public版として使う場合、ここに個人的すぎるメモを初期データとして入れないでください。  
公開リポジトリにすると、HTMLやCSVの中身は他人にも見える可能性があります。

## オフライン利用について

- オフライン対応は、GitHub PagesのようなHTTPS、または `localhost` などService Workerが使える環境で有効です。
- `file://` で直接 `index.html` を開いた場合、ブラウザ仕様によりService Workerは登録されません。
- メモ本文や添付画像は従来どおり端末内の `localStorage` に保存されます。

### GitHub Pagesで更新したとき

Service Workerは新しいバージョンを自動確認します。GitHub Pagesへ更新を反映した後、オンライン状態で一度ページを開くと、次回以降のオフライン起動に新しいアプリ本体が使われます。
