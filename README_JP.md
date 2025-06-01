# AGI タイムライン - ジュニアエンジニア向け解説書

## 📌 プロジェクト概要

「AGI タイムライン」は、人工汎用知能（AGI）の発展の歴史を可視化するインタラクティブなWebアプリケーションです。2015年から現在までの人工知能分野における重要な出来事、技術的ブレークスルー、文化的・社会的イベントを時系列で表示します。

🌐 **ライブサイト**: [ai-timeline.org](https://ai-timeline.org)

## 🎯 このプロジェクトの目的

- AI/AGI分野の歴史を分かりやすく可視化
- 技術的進歩と社会的影響の関係性を理解
- オープンソースコミュニティによる継続的な情報更新
- 研究者、開発者、一般ユーザーへの教育的価値の提供

## 🛠️ 技術スタック

### フロントエンド
- **React 19** - UIライブラリ
- **Vite** - 高速ビルドツール・開発サーバー
- **Tailwind CSS** - ユーティリティファーストなCSSフレームワーク
- **Three.js** - 3Dグラフィックス（背景エフェクト用）
- **Framer Motion** - アニメーションライブラリ
- **GSAP** - 高性能アニメーション

### 国際化対応
- **i18next** - 多言語対応ライブラリ
- **react-i18next** - React用i18nextバインディング
- 現在対応言語：英語、中国語

### 開発ツール
- **Prettier** - コードフォーマッター
- **Autoprefixer** - CSS自動プレフィックス

## 📁 プロジェクト構造解説

```
/
├── public/                    # 静的ファイル
│   ├── favicon.png           # ファビコン
│   ├── og-image.png          # OGPイメージ
│   └── time100cover.jpg      # TIME誌カバー画像
├── src/                      # ソースコード
│   ├── components/           # Reactコンポーネント
│   │   ├── EmergentBackground.jsx   # 背景3Dエフェクト
│   │   ├── EventCard.jsx            # イベントカード
│   │   ├── LanguageSwitcher.jsx     # 言語切り替え
│   │   └── Timeline.jsx             # メインタイムライン
│   ├── data/
│   │   └── timelineData.js          # タイムラインデータ
│   ├── App.jsx               # メインアプリケーション
│   ├── i18n.js              # 国際化設定
│   ├── index.css            # グローバルスタイル
│   └── main.jsx             # エントリーポイント
├── index.html               # HTMLテンプレート
├── package.json             # 依存関係・スクリプト
├── tailwind.config.cjs      # Tailwind設定
├── postcss.config.cjs       # PostCSS設定
└── vite.config.js           # Vite設定
```

### 重要なファイルの役割

#### `src/App.jsx`
- アプリケーションの最上位コンポーネント
- レイアウト構造の定義
- 言語切り替え機能の配置
- 背景エフェクトとタイムラインの統合

#### `src/data/timelineData.js`
- **最も重要なデータファイル**
- すべてのタイムラインイベントの定義
- カテゴリ分類（モデルリリース、文化・社会、ビジネス・産業、研究・論文、政策・規制）
- 多言語対応データ構造

#### `src/components/Timeline.jsx`
- タイムライン表示の核となるコンポーネント
- 複雑な状態管理（zoom、filter、layout）
- パフォーマンス最適化（React.memo、useMemo、useCallback）
- レスポンシブデザイン対応

#### `src/i18n.js`
- 国際化機能の設定
- 翻訳リソースの定義
- 言語切り替えロジック

## 🚀 開発環境セットアップ

### 前提条件
- Node.js 18以上
- npm または yarn

### セットアップ手順

1. **リポジトリのクローン**
```bash
git clone https://github.com/KaishuShito/AGI-timeline.git
cd AGI-timeline
```

2. **依存関係のインストール**
```bash
npm install
```

3. **開発サーバーの起動**
```bash
npm run dev
```

4. **ブラウザで確認**
- 通常 `http://localhost:5173` でアクセス可能
- ターミナルに表示されるURLを確認してください

### 利用可能なスクリプト

```bash
npm run dev         # 開発サーバー起動
npm run build       # 本番ビルド
npm run preview     # ビルド結果のプレビュー
npm run format      # コード整形
npm run format:check # コード整形チェック
```

## 🔧 主要機能の実装解説

### 1. タイムライン表示機能
- **ズーム機能**: 時間軸の拡大・縮小（1-8倍）
- **フィルタリング**: カテゴリ別イベント表示
- **レイアウト自動調整**: 画面サイズに応じた配置最適化

### 2. イベントカード
- **クリック可能リンク**: 外部ソースへの直接リンク
- **ホバーエフェクト**: インタラクティブなUI
- **重要度表示**: イベントの影響度による視覚的差別化

### 3. 3D背景エフェクト
- **Three.js**: WebGLベースの動的背景
- **パフォーマンス最適化**: フレームレート制御
- **レスポンシブ対応**: デバイス性能に応じた品質調整

### 4. 国際化対応
- **動的言語切り替え**: ページリロード不要
- **翻訳管理**: JSON形式での効率的な管理
- **日付フォーマット**: ロケール対応表示

## 🎨 デザインシステム

### カラーパレット
- **背景**: `#0a0a0f` (ダークネイビー)
- **テキスト**: 白系グラデーション
- **アクセント**: ブルー系 (`text-blue-400`)
- **ホバー**: `text-blue-300`

### フォント
- **セリフ**: EB Garamond (見出し用)
- **サンセリフ**: Inter (本文用)
- **レスポンシブ**: `text-4xl md:text-5xl`

### アニメーション
- **Framer Motion**: ページ遷移・カード動作
- **GSAP**: 高性能スクロールアニメーション
- **CSS Transitions**: ホバーエフェクト

## 🔄 コントリビューション方法

### 新しいイベントの追加

1. **データ追加**
   - `src/data/timelineData.js`を編集
   - 新しいイベントオブジェクトを配列に追加
   - 必要な情報：日付、タイトル、説明、カテゴリ、重要度

2. **フォーマット例**
```javascript
{
  start_date: { year: "2024", month: "01", day: "15" },
  text: {
    headline: createLink("https://example.com", "イベントタイトル"),
    text: "<p>イベントの詳細説明...</p>",
  },
  chinese: {
    headline: createLink("https://example.com", "中国語タイトル"),
    text: "<p>中国語での説明...</p>",
  },
  importance: 3, // 1-5 (5が最高)
  category: CATEGORIES.MODEL_RELEASE,
}
```

### 翻訳の追加

1. **新言語サポート**
   - `src/i18n.js`にリソース追加
   - `LanguageSwitcher.jsx`に言語オプション追加

2. **既存翻訳の改善**
   - 英語・中国語翻訳の精度向上
   - 文化的適応の考慮

## 🐛 よくある問題と解決法

### 開発環境の問題

**Q: `npm install`でエラーが発生する**
A: Node.jsのバージョンを確認（18以上推奨）、`npm cache clean --force`を実行

**Q: 開発サーバーが起動しない**
A: ポート5173が使用中の場合、別のポートを使用 `npm run dev -- --port 3000`

**Q: ビルドでメモリエラー**
A: Node.jsのメモリ制限を増加 `NODE_OPTIONS="--max-old-space-size=4096" npm run build`

### パフォーマンスの問題

**Q: スクロールが重い**
A: イベント数が多い場合、仮想スクロールの実装を検討

**Q: 3D背景でフレームレート低下**
A: `EmergentBackground.jsx`でパーティクル数を調整

## 📊 プロジェクトの技術的特徴

### パフォーマンス最適化
- **React.memo**: 不要な再レンダリング防止
- **useMemo/useCallback**: 計算結果のキャッシュ
- **Lazy Loading**: Timeline コンポーネントの遅延読み込み
- **Suspense**: ローディング状態の管理

### アクセシビリティ対応
- **semantic HTML**: 適切なHTML要素の使用
- **keyboard navigation**: キーボード操作対応
- **screen reader**: 読み上げソフト対応
- **color contrast**: 十分なコントラスト比

### SEO対策
- **meta tags**: 適切なメタデータ設定
- **Open Graph**: SNSシェア対応
- **structured data**: 検索エンジン最適化

## 🔮 今後の開発方向性

### 機能拡張
- **日本語対応**: 完全な日本語翻訳
- **検索機能**: イベント検索・フィルタリング強化
- **詳細ビュー**: イベント詳細ページ
- **データ可視化**: グラフ・チャート追加

### 技術改善
- **TypeScript化**: 型安全性の向上
- **テスト導入**: 単体・統合テスト
- **PWA対応**: オフライン機能
- **パフォーマンス監視**: Core Web Vitals最適化

## 🤝 学習リソース

### React関連
- [React公式ドキュメント](https://react.dev/)
- [Framer Motionガイド](https://www.framer.com/motion/)

### CSS/デザイン
- [Tailwind CSS公式](https://tailwindcss.com/)
- [Three.js学習リソース](https://threejs.org/docs/)

### 国際化
- [i18next公式ドキュメント](https://www.i18next.com/)

---

**このドキュメントは、AGI タイムラインプロジェクトに初めて参加するジュニアエンジニアが、プロジェクトの全体像を理解し、効果的にコントリビューションできるように作成されました。**

質問や改善提案があれば、ぜひIssueやPull Requestでお知らせください！