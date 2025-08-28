# BelieFi - Vibe Trading on belief. DeFAI Agent as NFT.

What if minting an NFT just once could have AI manage your assets for you?
We introduce BelieFi.

## Hackathon Info

- [Entry] [Agents of the Permaweb: The AO Hackathon](https://lu.ma/go6pt5yn?tk=BtRXD5)
- [Track] Practical Utility Agents
- [Tagline] Vibe trading on belief. DeFAI Agent as NFT
- [SpecialPrize]
  - RandAO: Generate NFT metadata (lucky_number) using on-chain randomness
  - AstroUSD: Improve Mint UX by accepting Mint Price in $USDA
  - ApusSDK: Evaluate Market Sentiment with Apus SDK and reflect it in AI Agent trading strategies (such as increasing DCA budget when Bullish)
  - Tate Agent: Prepare DeFAI NFT that concentrates investment in Community Labs' FLP
- [Demo] -
- [Process] -
- [X(Twitter)] x.com/xBelieFi

## [MARKET&ISSUES]

### Crypto Investing > Human Capacity

Thousands of protocols, 140,000 new token launches per day, price volatility, political situations.
The crypto market continues to exponentially increase entropy. Crypto investing has already exceeded human cognitive limits. In this context, AI × DeFi = DeFAI has inevitably gained attention. Autonomous management by AI is a burning need for everyone and the last piece of Web3.

### DeFAI = Hype (still)

However, "DeFAI" still remains in the realm of buzzwords.
The current reality is that no projects have emerged that define concrete UX and achieve PMF.

## [PROBLEM] Investment Challenges on AO

## [SOLUTION] BelieFi = Vibe Trading on belief + DeFAI Agent as NFT

We define "DeFAI = Vibe Trading" (abstraction of DeFi/crypto investing) and realize this UX with a single NFT mint.
This is supported by two concepts:
"Vibe Trading on belief" and "DeFAI Agent as NFT".

The NFT functions as an AI agent with its own wallet and signing authority, executing autonomous asset management on behalf of users according to predetermined strategies.
The investment strategy tied to each NFT is an abstraction of specific beliefs.
For example, an "AO MAXI" who believes that AO is the future of web3 would maximize holdings of $AO. Beliefs and convictions can be expressed as investment strategies.

## DeFAI NFT

1. AO MAXI: Maximize the number of $AO holdings
2. Permaweb Arbitrageur: Execute arbitrage against the appropriate price ratio between $AR and $AO. Also initially select the appropriate price ratio
3. Agent Tate: Concentrate investment in CommunityLabs' FLP
4. AO DeFi against AO Fair Launch: Address the issue that AO Fair Launch deposits have better investment efficiency than DeFi on AO

### AO MAXI

- [Belief] Believes that AO is the future of web3
- [Strategy] Maximize the number of $AO holdings
- [MintToken] Mint with $USDA → Automatically convert to $AO on the application side (Process handles AO internally)
- [Actions]
  - Dollar Cost Averaging: Use Dexi's cron trigger to purchase AO once daily on Botega
  - Market Sentiment: Analyze AO's Market Sentiment with Apus SDK, and if Bullish, reflect it in increased DCA budget
  - Yield Farming: Manage AO with single token through lending or liquid staking. However, since this pool doesn't exist yet, it will be implemented in the future
  - Smart Swap: Automatically swap purchase when $AO is unfairly underpriced on AO DEX

## [USERFLOW]

1. Select Belief from the list page (select "AO_MAXI" in this case)
2. Enter budget and mint on the mint page (10USDA in this case)
3. DeFAI NFT is minted
   1. Specifically, NFT (Atomic Assets), its associated Smart Wallet, and AI Agent Process are each deployed
   2. Mint Price is transferred 100% to Smart Wallet and becomes trading budget
   3. Market Sentiment (by ApusSDK) and Lucky Number (by RandAO) at mint time are also recorded as NFT metadata
4. DeFAI NFT starts trading with the mint amount as trading budget
5. When the deadline comes, the Smart Wallet budget is automatically transferred to the minting user's wallet.

## [FEATURES]

### Secondary Market Functionality and Unique NFT EXIT Strategies

While the MVP will use SBT, the next update will allow users to choose settings that enable secondary market trading.
This enables unique NFT EXIT strategies.
In BelieFi, users cannot withdraw from the NFT's Smart Wallet until the deadline.
Instead, users can EXIT early through secondary market trading.
The Smart Wallet budget becomes the Floor Price directly, allowing DEX liquidity to be handled on NFT Marketplaces.

### Safety Layer as NFT

In DeFi, users' wallets directly interact with smart contracts, which is structurally risky.
AO Process doesn't require Approve like EVM, but there's a risk of losing assets in users' wallets through careless operations when malicious code is embedded in Processes or frontends.
However, in BelieFi, users' wallets never directly interact with DeFi.
Additionally, since only the assets of independent NFT Smart Wallets serve as trading budgets, risks are distributed.

## [REVENUE] Fee Model

BelieFi achieves both stress-free UX and sustainable profitability.
First, we do not charge any fees at mint time. The Mint Price becomes the trading budget directly.
This is because it's overwhelmingly easier to understand.

Fees are only charged at EXIT time.
That is, either during automatic transfer after deadline expiration or during secondary market trading.
However, we will run campaigns that reduce fees for one or the other.
For example, when we want to boost AO NFTs, we will reduce secondary market trading fees.

## [TEAM] Founder Introduction

I am one of the most accomplished individuals in Japan's NFT space.
I have successfully achieved multiple NFT sales exceeding $500K and have also delivered results with B2B SaaS products utilizing NFTs. I take pride in having confronted both the expectations and disappointments surrounding NFTs head-on from the frontlines. This is precisely why I conceived "DeFAI Agent as NFT" as the most practical use case for NFTs.

Additionally, I have made the following contributions to Arweave:

- Co-host of Hyper Parallel Tokyo
- Host of Arweave AO Bootcamp
- Translated all articles from Community Labs, ARIO, Permaweb Journal into Japanese and published them for Japanese builders
- Implemented three App Chain PoCs as Solution Architect for L1 DA utilizing Arweave
