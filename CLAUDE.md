# プロジェクト概要

Twitter（X）の詳細検索URLを生成する個人向けGitHub Pagesツール。

## 設計決定

| 項目 | 内容 |
|------|------|
| ホスト | GitHub Pages（新規リポジトリ） |
| スタック | HTML + CSS + JS（ビルドなし、外部依存なし） |
| レイアウト | 左:フォーム / 右:URLプレビュー（2カラム） |
| URL更新 | リアルタイム（inputイベント） |
| 日付入力 | プリセット（今日/1週間/1ヶ月）＋ `<input type="date">` |
| アクション | クリップボードコピーボタン＋X で検索を開くボタン |
| 状態保存 | ページURLのクエリパラメータに検索条件を同期 |
| デザイン | Twitter/Xカラー（黒・白・青）ベース＋モダン・清潔感 |

## 対応する検索パラメータ

- キーワード: AND条件 / 完全一致 / OR条件 / 除外ワード / ハッシュタグ
- アカウント: from / to / mention
- 期間: since / until
- 言語: lang
- メディア: filter:images / filter:videos
- 返信: filter:replies（含める/のみ）トグル＋ラジオ形式
- リンク: filter:links（含める/のみ）トグル＋ラジオ形式
- エンゲージメント: min_replies / min_faves / min_retweets

## ファイル構成

```
twitter_search_url/
├── index.html       # メインページ（単一ファイル構成）
├── README.md
└── CLAUDE.md
```

単一の `index.html` にHTML・CSS・JSをすべて収める。外部CDN不使用。

## コーディング規則

- グローバルスコープの汚染を避けるため、すべてのJSは即時実行関数（IIFE）またはモジュールで囲む
- URLクエリパラメータとフォーム状態の同期は双方向で行う（フォーム変更→URL更新、URLロード→フォーム復元）
- Twitter検索クエリの組み立てロジックは独立した純粋関数として実装する
- z-indexは50を上限とする
- transitionは変化するプロパティを明示する（`all`は使わない）
