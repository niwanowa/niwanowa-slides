# スライド資料リポジトリ

このリポジトリは様々なトピックのプレゼンテーションスライド資料を管理するためのものです。

## リポジトリ構成

```
slides/
├── [スライド名1]/
│   ├── planning/     # 企画・案出し用ファイル
│   │   ├── outline.md
│   │   ├── content.md
│   │   └── content.pdf
│   ├── slide/        # スライド作成用ファイル
│   │   ├── slide.md
│   │   ├── images/   # スライドで使用する画像
│   │   └── fonts/    # スライドで使用するフォント
│   └── output/       # 生成されたスライド
│       ├── html/
│       ├── pdf/
│       └── pptx/
└── [スライド名2]/
    └── ...
```

## 現在のスライド一覧

1. [生成 AI 入門](./slides/generative-ai/) - 生成 AI の基礎と実用的なサービスの紹介

## 新しいスライドの追加方法

新しいスライドを追加する場合は、以下のコマンドでフォルダ構造を作成します：

```bash
mkdir -p slides/[スライド名]/{planning,slide/images,output/{html,pdf,pptx}}
```

## 使用方法

### Markdown から PDF の生成

```bash
cd slides/[スライド名]/planning/
pandoc content.md -o content.pdf --pdf-engine=xelatex -V mainfont="Hiragino Sans" -V CJKmainfont="Hiragino Sans" -V documentclass=article -V geometry:margin=1in
```

### スライドの生成 (Marp を使用)

```bash
cd slides/[スライド名]/
# HTMLとして出力
npx @marp-team/marp-cli slide/slide.md --html -o output/html/slide.html

# PDFとして出力
npx @marp-team/marp-cli slide/slide.md --pdf -o output/pdf/slide.pdf

# PowerPointとして出力
npx @marp-team/marp-cli slide/slide.md --pptx -o output/pptx/slide.pptx
```

## 注意事項

- 各スライドのフォルダには README.md を作成し、スライドの概要や特記事項を記載してください
- 画像ファイルは最適化してから追加することを推奨します
