# BitzUi

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

BitzUiは、BitzLabsエコシステム内で、UIレイアウトやワイヤーフレームを宣言的に定義し、描画するための専門ライブラリです。

## 主な機能

-   **`UIAST`の定義**: コンポーネントツリーと、その配置ルール（Flexbox風）を表現するためのAST。
-   **2つの入力ルート**:
    1.  **パーサー**: BitzLabs独自の直感的なDSL（ドメイン特化言語）を解釈し、`UIAST`を生成します。
    2.  **専用API (Builder API)**: C#やTypeScriptのコードから、コンポーネントオブジェクトを組み立てるようにして、`UIAST`をプログラム的に構築できます。
-   **レイアウトエンジン**: `UIAST`を受け取り、Flexbox風のアルゴリズムで各コンポーネントのサイズと位置を計算し、その結果を描画プリミティブの集合である**`LayoutAST`**として出力します。

## このライブラリの位置づけ

主に`BitzDoc`から利用され、Markdown文書内に画面のワイヤーフレームやコンポーネントの設計図を直接埋め込む機能を提供します。Mermaidなどでは難しい、手動での精密なレイアウト制御が可能です。

このライブラリの最終的な出力は`LayoutAST`です。これをSVGなどの具体的な画像形式に変換する処理は、`BitzRenderers`に委譲されます。

### 利用シナリオ

-   **DSL経由**: ソフトウェアの要求仕様書や設計書に、画面レイアウトのモックアップを記述する。
-   **API経由**: アプリケーションの現在の状態に基づいて、動的にUIのプレビューを生成する。

### 依存関係

-   `BitzAstCore`
-   `BitzParser`
-   `BitzLayout` (出力型として)

---
