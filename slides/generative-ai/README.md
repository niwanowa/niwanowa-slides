# 生成 AI 入門

このディレクトリには、生成 AI に関するプレゼンテーション資料が含まれています。

## ディレクトリ構造

- `slide/` - スライドのソースファイルとリソース
  - `fonts/` - スライドで使用するフォント
  - `images/` - スライドで使用する画像
- `output/` - 生成されたスライド
  - `html/` - HTML 形式のスライド
  - `pdf/` - PDF 形式のスライド
  - `pptx/` - PowerPoint 形式のスライド

## スライドの生成方法

スライドを生成するには、リポジトリのルートディレクトリで以下のコマンドを実行します：

```bash
# HTMLとして出力
npx @marp-team/marp-cli slide.md --html -o slides/generative-ai/output/html/slide.html

# PDFとして出力
npx @marp-team/marp-cli slide.md --pdf -o slides/generative-ai/output/pdf/slide.pdf

# PowerPointとして出力
npx @marp-team/marp-cli slide.md --pptx -o slides/generative-ai/output/pptx/slide.pptx
```

## 内容

このプレゼンテーションでは、以下のトピックについて説明しています：

1. 生成 AI の基本概念
2. 主要な生成 AI モデルとその特徴
3. 生成 AI の応用例
4. 実用的なサービスの紹介
5. 今後の展望と課題
