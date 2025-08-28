## AI Agent のアクション一覧

### 定期実行アクション（Dexi の cron トリガー）

#### 1. DCA（ドルコスト平均法）実行

```lua
-- 毎日実行される基本アクション
function ExecuteDailyDCA()
  local daily_budget = GetDailyBudget()  -- 5 USDA ÷ 365日
  local current_ao_price = GetCurrentPrice("AO", "USDA")

  -- Botegaで$USDA → $AO スワップ
  SwapOnBotega({
    from_token = "USDA",
    to_token = "AO",
    amount = daily_budget,
    slippage = 5.0
  })

  -- 取引記録
  RecordTransaction("DCA", daily_budget, current_ao_price)
end
```

#### 2. Portfolio Rebalancing

```lua
-- 週次または残高閾値で実行
function RebalancePortfolio()
  local current_usda = GetBalance("USDA")
  local current_ao = GetBalance("AO")
  local total_value = current_usda + (current_ao * GetPrice("AO"))

  local target_usda_ratio = 10  -- 10% USDA保持（運用継続用）
  local target_ao_ratio = 90    -- 90% AO保持

  if NeedsRebalancing(current_ratio, target_ratio) then
    ExecuteRebalance(target_usda_ratio, target_ao_ratio)
  end
end
```

### 条件付き実行アクション

#### 3. Smart Swap（価格閾値トリガー）

```lua
-- 価格が特定条件を満たした時のみ実行
function CheckSmartSwapConditions()
  local current_price = GetCurrentPrice("AO", "USDA")
  local nft_metadata = GetNFTMetadata()
  local lucky_number = nft_metadata.lucky_number

  -- Lucky Numberに基づく個別閾値
  local buy_threshold = CalculateBuyThreshold(lucky_number)

  if current_price < buy_threshold then
    ExecuteLargeSwap({
      amount = GetAvailableBalance("USDA") * 0.5,
      reason = "Smart Swap - Price Below Threshold"
    })
  end
end
```

#### 4. Market Sentiment 対応

```lua
-- Apus Network市場分析に基づく追加購入
function CheckSentimentBasedAction()
  local sentiment = GetMarketSentiment()  -- Apus Network
  local confidence = sentiment.confidence_score

  if sentiment.ao_sentiment == "very_bullish" and confidence > 0.9 then
    ExecuteBoostPurchase({
      multiplier = 1.5,  -- 通常DCAの1.5倍
      reason = "High Confidence Bullish Signal"
    })
  end
end
```

### 情報収集・分析アクション

#### 5. 市場データ収集

```lua
-- Dexiからの市場情報取得
function CollectMarketData()
  local market_data = {
    ao_price = GetPriceFromDexi("AO"),
    volume_24h = GetVolumeFromDexi("AO"),
    liquidity_depth = GetLiquidityFromDexi("AO/USDA")
  }

  StoreMarketData(market_data)
  return market_data
end
```

#### 6. Performance 追跡

```lua
-- エージェントの成績記録
function TrackPerformance()
  local performance = {
    total_trades = GetTradeCount(),
    total_ao_accumulated = GetAOAccumulated(),
    average_purchase_price = GetAveragePrice(),
    days_active = GetDaysActive()
  }

  UpdatePerformanceMetrics(performance)
end
```

## 実行スケジュール（簡略版）

| アクション       | 頻度     | トリガー                   | 実装優先度 |
| ---------------- | -------- | -------------------------- | ---------- |
| DCA 実行         | 毎日     | Dexi の cron メッセージ    | ⭐ 最高    |
| Market Data 収集 | 1 時間毎 | Dexi の cron メッセージ    | ⭐ 高      |
| Smart Swap 判定  | 30 分毎  | 価格変動検知               | 🔸 中      |
| Performance 追跡 | 日次     | 取引後                     | 🔸 中      |
| Sentiment 対応   | 1 時間毎 | センチメント変化           | 🔹 低      |
| Rebalancing      | 週次     | ポートフォリオ比率チェック | 🔹 低      |
