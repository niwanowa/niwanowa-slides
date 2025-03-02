# プルリクエスト作成手順

## 0.コミットする日を取得する

github 上のコントリビューションを継続するために、github のコントリビューショングラフを見て、コミットする日を取得する。
もし、コミットする日が連続していない場合は、コミットする日を取得する。
現在日までコミットが連続している場合は現在日時でコミットする。

## 1. 作業ブランチの作成

```bash
# メインブランチを最新化
git checkout main
git pull origin main

# 作業ブランチを作成
git checkout -b feature/branch-name
```

## 2. 変更の作成とコミット

```bash
# 変更を作成
# ...

# 変更をコミット
git add .
git commit -m "feat: 変更の説明"
```

## 3. リモートへのプッシュ

```bash
git push origin feature/branch-name
```

## 4. プルリクエストの作成

1. プルリクエストの説明を一時ファイルに作成

```bash
cat << 'EOF' > pr_description.md
## 変更内容

### 主な変更点
- 変更点1
- 変更点2

### 技術的な詳細
- 詳細1
- 詳細2

## テスト結果
- テスト内容
- 動作確認結果

## 今後の展開
- 次のステップ
- 残課題
EOF
```

2. プルリクエストの作成

```bash
# 一時ファイルを使用してプルリクエストを作成
gh pr create --title "feat: プルリクエストのタイトル" --body-file pr_description.md

# 一時ファイルを削除
rm pr_description.md
```

## 5. レビュー後の対応

- レビューコメントに基づいて修正
- 必要に応じて追加のコミットを作成
- プルリクエストの説明を更新する場合は同様の手順で一時ファイルを使用

## 注意点

- コミットメッセージは[Conventional Commits](https://www.conventionalcommits.org/)の形式に従う
- プルリクエストの説明は見やすく構造化する
- 大きな変更の場合は、変更内容を適切に分割する
