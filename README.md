# AI Code Reader

AIと作ったコードを自分の目で読み解く10日間の学習アプリ。

## ファイル構成

```
ai-code-reader/
├── index.html              ← アプリ本体
├── manifest.json           ← PWA設定
├── service-worker.js       ← オフライン対応
├── README.md               ← この手順書
└── icons/
    ├── icon-master.svg     ← マスターSVG（編集用）
    ├── icon-512.png        ← PWA高解像度
    ├── icon-192.png        ← PWA標準
    ├── icon-180.png        ← iOS用
    ├── icon-32.png         ← ファビコン
    ├── icon-16.png         ← ファビコン小
    └── icon-preview.png    ← プレビュー
```

## ローカルで使う

1. このフォルダを丸ごとどこかに置く
2. `index.html` をダブルクリック
3. ブラウザで開く

※ ローカル（`file://`）ではPWA機能（ホーム画面追加、オフライン対応）は動作しません。スマホで使うにはGitHub Pagesでホスティングしてください。

## GitHub Pagesにデプロイする手順

### 1. GitHubで新しいリポジトリを作成
- ブラウザで https://github.com/new にアクセス
- リポジトリ名：`ai-code-reader`（任意）
- **Public**を選択（無料アカウントでGitHub Pagesを使うため）
- 「Create repository」

### 2. GitHub Desktopでクローン or このフォルダを開く
- 既にこのフォルダがあるなら、GitHub Desktopで「Add Local Repository」
- もしくは新規にクローンしてからファイルをコピー

### 3. ファイル一式をコミット＆プッシュ
- GitHub Desktopで「Commit to main」→「Push origin」

### 4. GitHub PagesをWeb上で有効化
- GitHubのリポジトリページを開く
- 上部メニュー「Settings」をクリック
- 左サイドバーの「Pages」をクリック
- 「Source」を「Deploy from a branch」に
- Branchを「main」、フォルダを「/ (root)」にして「Save」
- 数分待つと、ページ上部に公開URLが表示される

### 5. スマホからアクセス
- 表示されたURL（例：`https://username.github.io/ai-code-reader/`）をスマホブラウザで開く
- iPhone：共有ボタン → 「ホーム画面に追加」
- Android：右上メニュー → 「ホーム画面に追加」
- これで普通のアプリのように起動できるようになります

## アイコンを変更したい場合

1. `icons/icon-master.svg` をテキストエディタかInkscape等で編集
2. 各サイズのPNGを再生成（Inkscapeでエクスポートするか、オンラインのSVG→PNG変換ツールを使う）
3. 同名で `icons/` 配下に上書き保存
4. `service-worker.js` の `CACHE_NAME` の数字を上げる（例：`v1` → `v2`）
   - これをやらないと、古いアイコンがキャッシュから返されて変わらないことがあります
5. コミット＆プッシュ
