# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## プロジェクト概要

AI支援によるMarpスライド生成ツール。MarkdownからプレゼンテーションスライドをAIの力を借りて効率的に作成する。

## コマンド

### 開発コマンド
```bash
# 依存関係のインストール
npm install

# スライドをプレビュー
npm run preview

# PDFとして出力
npm run build  

# ファイル監視モードでプレビュー
npm run watch

# Webサーバーで表示
npm run serve
```

## ファイル構成とワークフロー

### 主要ファイル
- `template.md` - 全スライドの基本テンプレート（Marpヘッダー、スタイル、表紙を含む）
- `marp-ai-rules.md` - AI生成時の厳格な制限ルール
- `input/` - 変換元Markdownファイル
- `images/` - ロゴ（`logo.png`）、背景（`background.png`）等の画像
- `generated/` - 生成されたスライド

### AIワークフロー
1. `input/`にMarkdownファイル配置
2. `marp-ai-rules.md`の制限に従ってスライド生成
3. `template.md`をベースとして使用
4. 生成後はpreview/buildコマンドで確認

## AI生成ルール（厳格遵守）

### 文字数制限
- タイトル: 最大40文字
- 本文: 1行50文字まで
- 1スライド: 最大500文字

### 構造制限  
- 最大行数: 15行/スライド
- 見出し: h1-h3まで
- リスト: 最大3階層
- 画像: 最大2枚/スライド
- 表: 最大1つ/スライド

### デザイン仕様
- 日本語フォント: Hiragino Sans, Noto Sans CJK JP
- 画像: 中央揃え、最大800px幅
- ヘッダーロゴ: `images/logo.png` (右上配置)
- 表紙背景: `images/background.png` (右下配置)

## 重要な注意点

- スライド生成時は必ず`marp-ai-rules.md`の制限を厳格に守る
- `template.md`のMarpヘッダー部分は変更しない
- 画像は必ず`images/`ディレクトリに配置
- ファイル名は`YYYYMMDD_[タイトル].md`形式で作成