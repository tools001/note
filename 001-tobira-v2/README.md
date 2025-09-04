# 避暑地への扉 — ノベルゲー風プロトタイプ（ChatGPT × Three.js × 単一HTML）

**短時間で「読めて動く」まで到達すること**を目的としたプロトタイプです。  
UIは単一HTMLで、背景はAI生成画像、演出は Three.js を用いた軽い表現（扉・雪・雷光・カメラ）です。

## デモ
- GitHub Pages: `https://<YOUR-USERNAME>.github.io/<REPO-NAME>/`  ← あなたのURLに置き換えてください

## 特徴
- ノベルゲーム風UI（テキスト枠／前へ・次へ／シーン切替）
- 背景は CSS `background-size: cover`、Three.js の `canvas` は JS 側で実サイズ管理（歪み防止）
- モバイル向けに DPR 上限（スマホ 1.5 / PC 2.0）・縦画面時 FOV/距離の微調整
- 軽演出（雪パーティクル／雷光フラッシュ／カメラワーク）

## クイックスタート
1. このリポジトリをクローン or ダウンロード  
2. `index.html` をブラウザで開く（オフラインでも動作可／CDNがブロックされる環境では下記参照）
3. `machi.png` / `hisyochi.png` / `hisyochi1.png` をお好みの画像に差し替え
4. 本文（テキスト配列）と `order` を編集

## 依存と配布（CDNポリシー）
今回は**再現性と手軽さ**を優先して、Three.js などは **CDN（jsDelivr）** から読み込んでいます。  
**バージョン固定（`@0.146.0`）**で挙動を安定化。展示やオフライン用途では**ローカル同梱**をおすすめします。

### CDN のスニペット（グローバル版）
```html
<script src="https://cdn.jsdelivr.net/npm/three@0.146.0/build/three.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/three@0.146.0/examples/js/controls/OrbitControls.js"></script>
<script src="https://cdn.jsdelivr.net/npm/three@0.146.0/examples/js/loaders/GLTFLoader.js"></script>
```

## ライセンス
- **コード**：MIT License（`LICENSE` を参照）
- **サードパーティ**：three.js（MIT）— 詳細は `THIRD_PARTY_NOTICES.md`
- **画像**：すべて**生成AI**による作者作成物（下記「アセットについて」参照）

## アセットについて
- 背景画像は**生成AI**で作成（ツール例：Stable Diffusion / Midjourney 等）。本リポジトリでは**生成物のみ**を格納しており、モデルや外部素材の権利は各提供元のライセンスに従います。
- 必要に応じて、使用ツール・モデル・プロンプト・生成日を `ASSETS.md` に追記してください。

## 既知の課題
- スマホ縦画面の最適化は未完（FOV/距離の自動調整、ノッチ安全域の更なる調整）
- 背景の色温度・粒状感の統一（将来的に生成AIで再生成して統一予定）
- 演出の連発抑止（1ビート=1演出の制御強化）

---
© 2025 <Your Name>
