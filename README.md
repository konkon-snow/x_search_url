# Twitter 詳細検索URL生成ツール

Twitter（X）の詳細検索URLをフォームから簡単に生成するツール。GitHub Pagesでホスト。

## 機能

- キーワード検索（AND / OR / 除外）
- アカウント指定（from / to / mention）
- 期間指定（プリセット＋日付ピッカー）
- 言語フィルタ
- メディアフィルタ（画像 / 動画 / リンク）
- 最小いいね数 / RT数
- 生成URLをリアルタイムプレビュー
- クリップボードコピー＋Twitterで直接開く
- 検索条件をURLクエリパラメータで保存・復元

## 技術スタック

- HTML + CSS + JavaScript（ビルドなし）
- GitHub Pages でホスト

## デプロイ

```bash
git push origin main
```

GitHub Pages の設定で `main` ブランチのルートを公開元に設定する。
