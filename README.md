# doc_genai_Using_Generative_AI_with_Mac_Mini_-Introduction-
Mac Miniでの生成AI活用（導入）

<br/><br/>
## 目次

- [はじめに](#はじめに)
- [イメージしていただくために](#イメージしていただくために)
  - [生成AIはスキルの１つ](#生成AIはスキルの１つ)
  - [生成AIの実体は大量の学習データを機械学習により詰め込んだファイル](#生成AIの実体は大量の学習データを機械学習により詰め込んだファイル)
  - [生成AIは入力に対して学習データに近い内容でランダムに回答しているだけ](#生成AIは入力に対して学習データに近い内容でランダムに回答しているだけ)
  - [生成AIを利用するにあたっての留意事項](#生成AIを利用するにあたっての留意事項)
- [生成AIの成り立ちや種類について](#生成aiの成り立ちや種類について)
  - [AIの種類](#aiの種類)
  - [生成AIの種類](#生成aiの種類)
  - [生成AIの活用事例](#生成aiの活用事例)
- [LLMの利用形態について](#llmの利用形態について)
  - [LLMの動作環境](#llmの動作環境)
  - [ローカルLLMを動作させる機器](#ローカルllmを動作させる機器)
  - [具体的なユースケース例](#具体的なユースケース例)
- [ローカルLLMの動作環境について](#ローカルllmの動作環境について)
  - [メモリ・演算装置](#メモリ・演算装置)
  - [アプリケーション](#アプリケーション)
  - [モデルサイズ](#モデルサイズ)
- [ローカルLLMの業務利用導入手順について](#ローカルllmの業務利用導入手順について)
  - [検証段階](#検証段階)
  - [運用段階](#運用段階)
  - [管理段階](#管理段階)
- [ローカルLLMの業務利用導入後の展望について](#ローカルllmの業務利用導入後の展望について)
  - [展望](#展望)
- [まとめ](#まとめ)
- [参考情報](#参考情報)

<br/><br/>
## はじめに

- Mac Apple siliconにより構成されたMac Miniを用いてローカルLLMによるAIチャット機能を導入し、業務効率化を実現することを目指します。
- 下記図表の印「■」については、この目的に沿って着目するべきキーワードに記しています。
- 下記図表ではキーワードのみ記しているため、詳細をご覧になりたい場合は、各章のリンクをご参照ください。

<br/><br/>
## イメージしていただくために
- リンクなし
### 生成AIはスキルの１つ

```mermaid
graph LR
    A[スキル] --> F[タッチタイピング]
    A --> G[ビジネスマナー]
    A --> B[インターネット検索]
    A --> C[SQL]
    A --> D[正規表現]
    A --> E[生成AI■]
```

<br/><br/>
### 生成AIの実体は大量の学習データを機械学習により詰め込んだファイル

```mermaid
graph LR
    A[大量のデータ] --> B[機械学習] --> |学習| C{生成モデル};
    A --> D[深層学習] --> |学習| C;
```

<br/><br/>
### 生成AIは入力に対して学習データに近い内容でランダムに回答しているだけ

```mermaid
graph LR
    G[プロンプト（入力）] --> E{生成モデル} --> |推論| F[新しいデータ<BR/>新しいコンテンツ];
```

<br/><br/>
### 生成AIを利用するにあたっての留意事項
- 2024年時点においては、以下のような課題があります。

```mermaid
graph LR
    A[生成AI] --> F[プロンプト次第で回答が変化する特性]
    A --> G[回答を見て使えないとやり直す必要がある]
    A --> B[利用することで逆に効率が下がるリスク]
    A --> E[プロンプトの情報量が多すぎると処理できない]
    A --> C[文章作成は得意だが論理的思考と計算は苦手]
    A --> D[生成モデルによって得意不得意がある]
```






<br/><br/>
## 生成AIの成り立ちや種類について
https://github.com/SparklingDetergent/doc_genai_About_the_origins_and_types_of_generative_AI/blob/main/README.md
### AIの種類

```mermaid
graph LR
    A[AIの種類] 
    A --> C[従来のAI]
    A --> D[生成AI■]
```

<br/><br/>
### 生成AIの種類

```mermaid
graph LR
    A[生成AIの種類] --> B[画像生成]
    A --> C[テキスト生成・LLM■]
    A --> D[動画生成]
```

<br/><br/>
### 生成AIの活用事例

| 分野 | 活用例 |
|------|--------|
| マーケティング | 広告文言生成 |
| カスタマーサービス | チャットボット |
| 業務■ | レポート作成支援 |
| 教育 | 個別化学習コンテンツ |
| 医療 | 診断支援 |
| エンターテイメント | ゲームシナリオ生成 |

<br/><br/>
## ローカルLLMの有用性について
https://github.com/SparklingDetergent/doc_genai_The_usefulness_of_local_LLM/blob/main/README.md
### LLMの動作環境

```mermaid
graph LR
    A[LLMの動作環境] --> B[クラウドサービス上のLLM]
    A --> C[クラウド環境へデプロイするLLM]
    A --> D[ローカル環境で動作するLLM■]
```

**補足**: ローカル環境で動作するLLMについては、Hugging Face等のサイトで配布されているモデルを、ライセンスに応じて利用可能です。

<br/><br/>
### ローカルLLMを動作させる機器

```mermaid
graph LR
    A[動作機器] --> B[ワークステーション]
    A --> C[エッジサーバー■]
    A --> D[AI専用機器]
```

<br/><br/>
### 具体的なユースケース例

| ユースケース | 説明 |
|--------------|------|
| 社内情報検索システム | 社内文書の効率的な検索・要約 |
| 顧客対応チャットボット | 24時間対応の自動応答 |
| コーディング支援■ | プログラミング補助・デバッグ支援 |
| オフライン翻訳 | インターネット接続不要の翻訳 |
| 医療現場での診断支援 | 症状に基づく初期診断補助 |

<br/><br/>
## ローカルLLMの動作環境について
https://github.com/SparklingDetergent/doc_genai_About_the_local_LLM_operating_environment/blob/main/README.md
### メモリ・演算装置

| メモリ種類 | 演算装置 |
|------------|----------|
| RAM | CPU |
| VRAM | GPU |
| 共有メモリ■ | CPU, GPU, NPU |

<br/><br/>
### アプリケーション

```mermaid
graph LR
    A[アプリケーション] --> B[Transformers]
    A --> C[llama.cpp■]
    A --> D[MLX]
    A --> E[ONNX Runtime]
```

<br/><br/>
### モデルサイズ

```mermaid
graph LR
    A[モデルサイズ] --> B[1-3B]
    A --> C[3-9B]
    A --> D[9-27B■]
    A --> E[27B以上]
```

<br/><br/>
## ローカルLLMの業務利用導入手順について
https://github.com/SparklingDetergent/doc_genai_About_the_introduction_procedure_for_business_use_of_LocalLLM/blob/main/README.md
### 検証段階

```mermaid
graph TD
    A[検証段階] --> B[検証期間]
    A --> C[ログ分析■]
    A --> D[業務成果との比較]
    A --> E[効果検証]
```

<br/><br/>
### 運用段階

```mermaid
graph TD
    A[運用段階] --> B[マニュアル化]
    A --> C[展開]
    A --> D[継続的な改善■]
```

<br/><br/>
### 管理段階

```mermaid
graph TD
    A[管理段階] --> B[新モデルと機器の評価]
    A --> C[スケーラビリティの検討]
    A --> D[評価体制の構築]
    A --> E[評価手順の整備■]
```

<br/><br/>
## ローカルLLMの業務利用導入後の展望について
- リンクなし
### 展望

```mermaid
graph LR
    A[展望] --> B[マルチモーダル導入■]
    A --> C[RAG導入]
    A --> D[エージェント技術導入]
    A --> E[LLMアプリケーション導入]
```

<br/><br/>
## まとめ

ローカルLLMの導入により、セキュリティを確保しつつ、業務効率化を実現できます。継続的な評価と改善が重要です。

<br/><br/>
## 参考情報

- 参考として、Mac Mini M1 のセットアップ手順を示します。
 - https://github.com/SparklingDetergent/doc_genai_Using_Generative_AI_with_Mac_Mini_M1_-Server_Setup-/blob/main/README.md
- 参考として、ログ分析に役立つチャットスクリプトを示します。
 - https://github.com/SparklingDetergent/src_genai_Script_to_use_local_LLM_with_llama.cpp_and_PowerShell


