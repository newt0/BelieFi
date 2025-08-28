# BelieFi - Vibe Trading on belief. DeFAI Agent as NFT.

“もし、NFT を 1 回ミントするだけで、AI があなたの資産を運用してくれるとしたら？”

私たちは BelieFi を紹介します。

## Hackathon Info

- [Entry] [Agents of the Permaweb: The AO Hackathon](https://lu.ma/go6pt5yn?tk=BtRXD5)
- [Track] Practical Utility Agents
- [Tagline] Vibe trading on belief. DeFAI Agent as NFT
- [SpecialPrize]
  - RandAO: NFT のメタデータ(luckyy_number)をオンチェーン乱数で生成
  - AstroUSD: Mint Price を $USDA で受け付けることで、Mint UX を向上
  - ApusSDK: Market Sentiment を Apus SDK で評価して、AI Agent のトレード戦略に反映（Bullish なら DCA の予算を増やすなど）
  - Tate Agent: Community Labs の FLP に集中投資する DeFAI NFT を用意
- [Demo] -
- [Process] -
- [X(Twitter)] x.com/xBelieFi

## [MARKET&ISSUES]

### Crypto Investing > Human Capacity

数千のプロトコル、1 日あたり 14 万件の新規トークン発行、価格変動、政治情勢。
クリプト市場は、指数関数的にエントロピーを増大させ続けています。 クリプト投資は、もはや人間の認知限界を超えています。 そんな中、 必然的に注目されたのが AI × DeFi = DeFAI。 AI による自律運用は、万人にとってのバーニングニーズであり、Web3 のラストピースです。

### DeFAI = Hype (still)

しかし、「DeFAI」は、まだバズワードの域を出ません。
具体的な UX を定義し、PMF を達成しているプロジェクトはまだ登場していないのが現状です。

## [PROBLEM] AO 上の投資課題

## [SOLUTION] BelieFi = Vibe Trading on belief + DeFAI Agent as NFT

私たちは「DeFAI ＝ Vibe Trading」（DeFi/クリプト投資の抽象化）と定義し、その UX を NFT のミント 1 回で実現します。

これを支えるのが二つのコンセプト。
「Vibe Trading on belief」 そして 「DeFAI Agent as NFT」。

NFT は自らのウォレットと署名権限を持つ AI エージェントとして機能し、定められた戦略に従い、ユーザーに代わり自律的な資産運用を実行します。

それぞれの NFT に紐づく投資戦略は、特定の信念を抽象化したものです。
たとえば、AO こそ web3 の未来だと信じる「AO MAXI」なら＄ AO の保有数を最大化するなど、信念や確信は投資戦略として表現できます。

## DeFAI NFT

1. AO MAXI: $AO の保有枚数を最大化する
2. $AR-$AO アービトラージャー: AR と AO 間の適正な価格比率に対してアービトラージを実行する。また、適正な価格比率を最初に選ぶ
3. AO DeFi against AO Fair Launch: AO Fair Launch のデポジットの方が、AO 上の DeFi より投資効率が良いという課題に向き合う
4. Agent Tate: CommunityLabs の FLP に集中投資する

### AO MAXI

- [Belief]
- [Strategy]
- [MintToken] $USDA でミント → アプリケーションサイドで $AO に自動変換(Process 内では AO を扱う)
- [Actions]
  - ドルコスト平均法: Dexi の cron トリガーで、Botega 上で AO を毎日一回購入
  - Market Sentiment: Apus SDK で AO の Market Sentiment を分析して、Bullish なら、DCA の予算増加に反映
  - Yield Farming: レンディングやリキッドステーキングなどで、AO をシングルトークンで運用。ただし、まだこのプールはないため、将来的に実装
  - Smart Swap: AO DEX 上で $AO が価格不当に低い時に、自動でスワイプ購入

## [USERFLOW]

1. 一覧ページから Belief を選ぶ（今回は「AO_MAXI」を選ぶ）
2. ミントページで、予算を入力して、ミント（今回は 10USDA）
3. DeFAI NFT がミントされる
   1. 具体的には、NFT（Atomic Assets）とそれに紐づく Smart Wallet、そして AI Agent という Process がそれぞれデプロイ
   2. Mint Price が 100%Smart Wallet に送金され、トレード予算となる
   3. NFT のメタデータとして、ミント時の Market Sentiment なども記録される
4. ミント額をそのままトレード予算として、DeFAI NFT がトレード開始
5. 期限が来たら、自動で Smart Wallet の予算がミントしたユーザーのウォレットへ送金される。このと

## Features

### 二次流通機能と NFT ならではの EXIT 戦略

MVP においては SBT とするが、次のアップデートでは二次流通可能な設定を選べるようにする。
これにより、NFT ならではの EXIT 戦略が可能となる。
BelieFi では期限まで NFT の Smart Wallet から引き出すことはできない。
その代わりに、ユーザーは二次流通によって 早期に EXIT することが可能となる。
Smart Wallet の予算がそのまま Floor Price となり、DEX の流動性を NFT Marketplace 上で扱うことができる。

### Safety Layer as NFT

DeFi は、ユーザーのウォレットが直接スマートコントラクトと関与しますが、これは構造的にリスキーです。
AO Process は EVM のように Approve は必要はありませんが、Process やフロントエンドに悪意あるコードが仕込まれており、迂闊な操作によってユーザーのウォレット内の資産を失うリスクがあります。
しかし BelieFi では、ユーザーのウォレットが直接 DeFi と関わることはありません。
また、独立した NFT の Smart Wallet の資産のみがトレード予算となるため、リスクが分散されます。

## [REVENUE] Fee Model

BelieFi はストレスフリーな UX と、持続的な収益性を両立します。
まず、ミント時に手数料は一切取りません。Mint Price がそのままトレード予算となります。
その方が圧倒的にわかりやすいからです。

手数料を取るのは、EXIT 時のみです。
つまり、期限終了後の自動送金か、あるいは二次流通の時です。
ただし、どちらかの手数料を引き下げるキャンペーンを行います。
例えば、AO の NFT を盛り上げたい時には二次流通手数料を引き下げます。

## [TEAM] ファウンダー紹介

私は、日本の NFT 領域において最も実績のある一人です。
これまでに Over $500K の NFT セールを複数回成功させ、さらに NFT を活用した B2B SaaS プロダクトでも成果を上げてきました。
現場の最前線で、NFT への期待と失望の両方に真正面から向き合ってきたと自負しています。
だからこそ私は、NFT の最も実用的なユースケースとして、「DeFAI Agent as NFT」を考案しました。

また、Arweave においては、下記のような貢献を行ってきました。

- Hyper Parallel Tokyo の Co-host
- Arweave AO Bootcamp の Host
- Community Labs, ARIO,Permaweb Journal などの記事を全て日本語に翻訳して、日本のビルダー向けに公開
- Arweave を活用した L1 DA にて、Solution Architect として三つの App Chain PoC を実現
