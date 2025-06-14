# Marp AI スライド生成ツール

MarpとAIを使用してMarkdownからプレゼンテーションスライドを効率的に生成するツールです。

## 特徴

- ✅ Cursor依存を排除した純粋なMarp環境
- 🤖 AI対応のスライド生成ルール
- 📝 テンプレートベースの一貫したデザイン
- 🎨 日本語フォント対応
- 🖼️ 画像とロゴの自動配置

## セットアップ

### 1. 依存関係のインストール
```bash
npm install
```

### 2. Marp拡張機能の設定
VS Codeを使用している場合、「Marp for VS Code」拡張機能をインストールしてください。

### 3. ディレクトリ構成
```
marp/
├── template.md           # スライドテンプレート
├── marp-ai-rules.md     # AI生成ルール
├── input/               # 入力Markdownファイル
│   └── sample.md
├── images/              # 画像ファイル
│   ├── logo.png        # ロゴ画像（必要に応じて）
│   └── background.png  # 背景画像（必要に応じて）
└── generated/          # 生成されたスライド
```

## 使用方法

### 1. 入力ファイルの準備
`input/` ディレクトリに変換したいMarkdownファイルを配置します。

### 2. AIでスライド生成
AIアシスタント（Claude、ChatGPT等）に以下のように指示してください：

```
`marp-ai-rules.md`のルールに従って、`input/sample.md`を元にMarpスライドを生成してください。
テンプレートは`template.md`を使用してください。
```

### 3. プレビュー・ビルド
```bash
# スライドをプレビュー
npm run preview

# PDFとして出力
npm run build

# ファイル監視モードでプレビュー
npm run watch

# Webサーバーで表示
npm run serve
```

## AI生成ルール

詳細なルールは `marp-ai-rules.md` を参照してください。

### 主要な制限事項
- **1スライドあたり**: 最大500文字、15行
- **画像**: 1スライドあたり最大2枚
- **見出し**: h1-h3まで
- **リスト**: 最大3階層

## カスタマイズ

### テンプレート変更
`template.md` を編集してスライドのデザインやスタイルを変更できます。

### 画像の配置
- ロゴ: `images/logo.png`
- 背景: `images/background.png`
- その他の画像も `images/` ディレクトリに配置

## トラブルシューティング

### 日本語フォントが表示されない
システムに以下のフォントがインストールされていることを確認してください：
- Hiragino Sans
- Noto Sans CJK JP

### 画像が表示されない
- 画像パスが正しいか確認
- `images/` ディレクトリに画像が配置されているか確認
- 画像ファイル名に日本語や特殊文字が含まれていないか確認
