![68a4d117da4ca476344f6d28f88e141a18e870cacbed9b6ed4d91d5b](https://github.com/user-attachments/assets/cde3cf11-4c53-4335-8eda-1e0dc6297dbb)

# PraisonAI-sandbox

## プロジェクト概要
このリポジトリはPraisonAIのサンドボックス環境です。AIエージェントを使用して創造的なコンテンツを生成する実験的な環境として設計されています。

## ディレクトリ構造
```
└─ PraisonAI-sandbox/
   ├─ example/
   │  ├─ simple/              # 基本実装例
   │  │  ├─ agents.yaml      # エージェント設定
   │  │  └─ tools.py         # カスタムツール定義
   │  └─ simple-docker/      # Docker環境での実装例
   │     ├─ agents.yaml      # エージェント設定
   │     ├─ config.toml      # Chainlit UI設定
   │     ├─ docker-compose.yml # Docker構成
   │     ├─ Dockerfile.ui    # UIコンテナ定義
   │     └─ tools.py         # カスタムツール定義
   └─ .SourceSageignore      # SourceSage除外設定
```

## 主要コンポーネント

### 🤖 AIエージェント構成
プロジェクトには3つの専門エージェントが含まれています：

1. **研究者（Researcher）**
   - 火星環境と猫の生態学の研究
   - 使用ツール：search_tool, wikipedia_tool
   - 最小/最大リフレクション回数：1-2回

2. **ストーリーデザイナー（Story Designer）**
   - 科学的正確性とエンターテイメント性の融合
   - 使用ツール：text_generation_tool
   - 研究者の結果に基づいてストーリーを展開

3. **脚本家（Scriptwriter）**
   - 映画脚本の作成
   - 使用ツール：writing_assistant_tool
   - ストーリーデザイナーの出力に基づいて脚本を作成

### 🛠 技術スタック
- **フレームワーク**: PraisonAI
- **UI**: Chainlit
- **実行環境**: Python 3.11
- **コンテナ化**: Docker対応
  - UIポート: 8082
  - 必要なPythonパッケージ:
    - praisonaiagents>=0.0.4
    - praisonai_tools
    - praisonai==2.0.18
    - praisonai[ui]
    - praisonai[crewai]

## 使用方法

### 基本実装（example/simple）
1. `agents.yaml`でエージェントの設定を確認
2. `tools.py`で必要なカスタムツールを追加
3. PraisonAIフレームワークを使用して実行

### Docker環境（example/simple-docker）
1. 環境変数を`.env`ファイルに設定
2. Dockerコンテナをビルド：
   ```bash
   docker-compose build
   ```
3. サービスを起動：
   ```bash
   docker-compose up
   ```
4. ブラウザで`http://localhost:8082`にアクセス

## プロジェクト統計
- 総ファイル数：10
- 総行数：357行
- 主要設定ファイル：
  - config.toml（118行）
  - agents.yaml（56行）
  - Dockerfile.ui（28行）
