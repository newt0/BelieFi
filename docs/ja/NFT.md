# Atomic Assets 開発要件

## 基本仕様

### NFT メタデータ

- name: "AO MAXI #[番号]"
- description: "AO の成長を信じる"
- strategy: "$AO を最大化する"
- image: 静的画像（コレクション内統一）
- external_url: 適宜設定
- lucky_number: RandAO から生成された数値（0-999）
- market_sentiment: Apus Network からの市場分析データ

### Mint 仕様

- 方式: Allow List 方式のみ
- Allow List: 外部データ参照方式（100-200 アドレス）
- 制限: 1 アドレスあたり 1 回のみ Mint 可能
- 価格: 5 $USDA（または$AO に変換）
- 発行上限: Allow List のアドレス数と同数
- Mint Price 受取先: NFT 専用 Smart Wallet

## 技術実装要件

### Lua Process 実装項目

1. NFT メタデータ管理機能
2. Allow List 検証ロジック
3. アドレス毎 Mint 制限チェック
4. RandAO 連携による lucky_number 生成
5. Apus Network 連携による market_sentiment 生成
6. $USDA支払い処理（または$AO での支払い受付）
7. Smart Wallet への mint 収益転送機能
8. NFT と Smart Wallet の 1:1 紐付け機能

### 外部連携要件

1. RandAO Module 統合

   - generateUUID()機能
   - requestRandom()機能
   - ランダムレスポンス処理

2. Apus Network 連携

   - 市場センチメント分析
   - $AO トークン関連データ取得
   - 信頼度スコア生成

3. Allow List 管理
   - 外部プロセスまたは TXID からの読み込み
   - アドレス検証機能
   - 動的更新対応

### データ構造

```
NFT_METADATA = {
  name: string,
  description: string,
  strategy: string,
  image: string,
  external_url: string,
  lucky_number: number,
  market_sentiment: {
    ao_sentiment: string,
    confidence_score: number,
    analysis_timestamp: string,
    market_factors: array,
    sentiment_source: string
  }
}

MINT_STATE = {
  total_minted: number,
  minted_by_address: table,
  allow_list_source: string,
  mint_price: number,
  base_token: string
}
```

### Handler 実装要件

1. Info Handler: プロセス情報と統計の返却
2. Mint Handler: Mint 実行処理
3. Transfer Handler: NFT 転送処理
4. Balance Handler: 残高確認
5. Allow-List Handler: 許可リスト確認
6. Metadata Handler: NFT メタデータ返却

### 制約・制限

1. Public Mint 機能は実装しない
2. Allow List はハードコードではなく外部参照
3. 1 アドレス 1 回制限の厳格な実装
4. Smart Wallet との確実な紐付け
5. RandAO と Apus Network の統合エラー処理

### 成功条件

1. Allow List アドレスから正常に Mint できること
2. 制限外アドレスから Mint できないこと
3. 1 アドレス複数回 Mint ができないこと
4. lucky_number が正常に生成されること
5. market_sentiment データが取得できること
6. Mint 収益が Smart Wallet に転送されること
7. NFT と Smart Wallet が正しく紐付けられること
