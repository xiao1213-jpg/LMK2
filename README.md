# リトル・ミュー診断｜GitHub Pages公開版

公開予定URL：[https://xiao1213-jpg.github.io/LMK2/](https://xiao1213-jpg.github.io/LMK2/)

## このフォルダに入っているもの

- `index.html`：診断本体
- `assets/`：4シリーズの背景画像、共有機能、アクセス解析設定
- `share/`：24結果それぞれのLINE・SNS共有用ページ
- `privacy.html`：アクセス解析についての説明
- `.nojekyll`：GitHub Pages用設定

## 1．新しいリポジトリを作る

既存の `LMK1` はHollis Pigeonholesが使用中なので、上書きしないでください。

1. GitHub右上の `＋` → `New repository`
2. Repository nameを **`LMK2`** にする
3. `Public`を選ぶ
4. README等を追加せず、`Create repository`

リポジトリ名を変えると、共有ページに設定済みのURLも変える必要があります。

## 2．ファイルをアップロードする

1. このZIPをパソコン上で展開する
2. GitHubの新しいリポジトリで `uploading an existing file` を押す
3. **展開したフォルダの中身**をすべてドラッグする
4. `Commit changes`

ZIPそのものをアップロードしてもサイトにはなりません。`index.html` がリポジトリ直下に見える状態にします。

## 3．GitHub Pagesを有効にする

1. リポジトリの `Settings`
2. 左側の `Pages`
3. Build and deploymentのSourceを `Deploy from a branch`
4. Branchを `main`、フォルダを `/(root)`
5. `Save`

数分後、次のURLを開きます。

`https://xiao1213-jpg.github.io/LMK2/`

## 4．Google Analyticsで回答数を確認する

Google AnalyticsでWebデータストリームを作り、`G-`から始まる測定IDを取得します。

その後、GitHub上で `assets/config.js` を開き、鉛筆ボタンから次の空欄へ貼ります。

```js
gaMeasurementId: "G-XXXXXXXXXX"
```

保存後、次のイベントが記録されます。

| イベント | 意味 |
|---|---|
| `diagnosis_start` | 診断を始めた回数 |
| `diagnosis_complete` | 15問を終えて結果に到達した回数 |
| `share` | LINE・共有・画像保存・リンクコピーの実行回数 |
| `restart` | もう一度診断した回数 |

回答者数を見るときは、Google Analyticsのイベント一覧で `diagnosis_complete` を確認します。結果別に見るため、イベントパラメータ `result_id` をイベントスコープのカスタムディメンションとして登録すると、24結果の分布も集計できます。

測定IDが空欄の間は、アクセス解析データを送信しません。

## 共有機能

- LINE：結果名と結果専用URLをLINEへ渡します。
- Instagram・DM：端末の共有画面へ1080×1350pxの結果画像を渡します。
- 結果画像を保存：同じ結果画像をPNGで保存します。
- リンクをコピー：LINE等でプレビューされる結果専用URLをコピーします。

Instagramが共有先に出ない端末では、結果画像を保存して投稿してください。
