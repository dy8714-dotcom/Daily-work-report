# 📋 Daily-work-report

毎日の作業日報 — ガス関連業務の日報を効率的に記録・管理するWebアプリケーション

## ✨ 主な機能

### 📝 案件入力
- 地域・時間・住居・区分・圧力・ガス器具・プランの7項目を記録
- 具体的問題とフィードバックを案件ごとに記載
- **省略モード**: ①〜⑦の入力をスキップし、⑧⑨のみで素早く登録可能
- 音声入力対応（Web Speech API）

### 📅 日付管理
- 日付ごとにデータを管理
- 前日/翌日ナビゲーション
- カレンダーからの日付ジャンプ

### 📊 出力機能
- **PDF保存**: 1日分の日報をA4形式のPDFとしてダウンロード
- **CSV保存**: Excel等で開けるCSVファイルとしてダウンロード
- **テキストコピー**: 日報内容をクリップボードにコピー
- **週間まとめコピー**: 過去7日分のサマリーをコピー
- **JSON出力/取込**: データのバックアップと復元

### 📝 総括・備考
- 1日の総括と備考を記録
- 広い入力エリア（4行テキストエリア）
- 登録済み案件一覧と並んで表示
- 音声入力対応

### 🔐 Firebase連携
- **Googleログイン**: Googleアカウントでワンクリックログイン
- **リアルタイムデータ同期**: Firestore によるクラウド保存
- **マルチデバイス対応**: PC・スマホ・タブレットでデータを一元管理
- **オフラインモード**: ログインせずにlocalStorageのみで利用可能
- **オフラインキャッシュ**: Firestoreのオフライン永続性により、通信不安定な環境でも動作

## 🚀 使い方

### Webで使う
GitHub Pagesで公開:
```
https://dy8714-dotcom.github.io/Daily-work-report/
```

### ローカルで使う
1. `index.html` をダウンロード
2. ブラウザで開く
3. 「オフラインで使う」を選択

## 📱 スマホでの使い方

1. ブラウザでURLを開く
2. Googleアカウントでログイン
3. PCと同じデータにアクセス可能

### iPhone/iPad
Safari > 共有ボタン > ホーム画面に追加

### Android
Chrome > メニュー(⋮) > ホーム画面に追加

## 🔧 技術仕様

- HTML / CSS (Tailwind CSS) / JavaScript（単一ファイル構成）
- Firebase Authentication（Googleログイン）
- Cloud Firestore（データ同期・オフラインキャッシュ）
- Web Speech API（音声入力）
- html2pdf.js（PDF出力）
- レスポンシブデザイン対応

### Firebase構成
- プロジェクト: daily-work-report-e1d8a
- 認証: Google プロバイダ
- データベース: Cloud Firestore
- セキュリティルール: ユーザーごとのデータ分離

### Firestoreデータ構造
```
users/{userId}/reports/{dateKey}
  ├── entries: [案件配列]
  ├── summary: "総括テキスト"
  ├── notes: "備考テキスト"
  └── updatedAt: タイムスタンプ
```

## 📝 更新履歴

### v2.0 (2026-03-21)
- Firebase連携（Googleログイン + Firestoreデータ同期）
- 入力省略ボタン追加（①〜⑦をスキップして⑧⑨のみで登録可能）
- 総括・備考を4行テキストエリアに拡大し、一覧下部に配置
- PDF出力機能追加（html2pdf.js）
- CSV出力機能追加
- テキストコピー機能改善
- 承認済みドメインにGitHub Pagesを追加

### v1.0
- 初期リリース
- 案件登録・編集・削除
- 日付別データ管理
- 音声入力対応
- JSON出力/取込
- 日報テキストコピー・週間まとめコピー

## 📄 ライセンス

MIT License

---

**Made with ❤️ for better daily reporting**
