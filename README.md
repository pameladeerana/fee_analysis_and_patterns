# Fee Analysis and Patterns

## Description
Simple fee analysis for the past 7 days (Oct 26 - Nov 1, 2026). Explores how ETH moves and how gas fees behaved after the Binance hack activity spike. Shows top senders, first wallet activity, EIP-1559 breakdown, rolling gas average, and base fee change between blocks. All values stored in wei and converted to ETH (1 ETH = 1e18 wei).

## 1. Parts / Statements

**1. ETH Value Transferred Per Sender**
Top 10 addresses by total ETH sent in successful transactions in the 7-day dataset. Values in wei converted to ETH. Short address format first 6 + last 4 chars, no 0x. Highest is 28c6c0...1d50 with 337,188 ETH.

**2. First Transaction Per Wallet**
Finds the first transaction for each wallet using window functions (ROW_NUMBER). Shows when a wallet first became active in the 7-day period. Uses window functions / window row number.

**3. EIP-1559 Fee Breakdown**
Breakdown of EIP-1559 in past 7 days: base fee + priority fee = total fee by transaction hash, total is sum of both in wei. Breakdown is by transaction hash (tx_hash). Highest total gas is 55.42 ETH converted from wei, sorted highest to lowest, limit to 10. Values in wei converted to ETH (1 ETH = 1e18 wei). Base fee reacts to block congestion & is burned, priority fee is for validators.

**4. 3-Block Rolling Average Gas Price**
Calculates 3-block rolling average gas price to smooth spikes. Uses gas and fees / rolling average. Shows trend during Oct 29 spike.

**5. Base Fee Change Between Consecutive Blocks**
Daily / block change of base fee between consecutive blocks. Uses window functions / window lag lead. Shows +5.69 gwei spike on Oct 29 after Binance hack, then -4.77 gwei drop on Oct 30.

## 2. Workflow

1. Explored tables on Dune, picked the block range for last 7 days (Oct 26 - Nov 1, 2026)
2. Queried dataset for 5 parts (assisted with WizardsCamp and AI for automation of queries)
3. Made visualizations and built final dashboard

## 3. Files

- **README.md** - This file
- **DuneQueries**
  - Part 1 - ETH Value Transferred Per Sender: https://dune.com/queries/9054921/13111892?sidebar=none
  - Part 2 - First Transaction Per Wallet: [Link]
  - Part 3 - EIP-1559 Fee Breakdown: https://dune.com/queries/9057825/13106291?sidebar=none
  - Part 4 - 3-Block Rolling Average Gas Price: [Link]
  - Part 5 - Base Fee Change Between Consecutive Blocks: [Link]
- **Dune Dashboard**: [Dashboard Link]

Embeds:
- Part 1: https://dune.com/embeds/9054921/13111892
- Part 3: https://dune.com/embeds/9057825/13106291

## 4. Snapshot and Data Coverage

- **Snapshot Date:** October 26 - November 1, 2026
- **Blocktime Range:** 2026-10-26 00:00:00 UTC to 2026-11-01 23:59:59 UTC (from query_9055030)
- **Block Number Range:** Run in Dune: SELECT MIN(number), MAX(number) FROM ethereum.blocks WHERE time BETWEEN '2026-10-26' AND '2026-11-01' (fill exact numbers here)

## 5. Tools

- Dune Analytics
- WizardsCamp
- LLM Meta AI

## Author

Pamela Dee
@0x_pameladee
GitHub: github.com/pamelad...
Building blockchain analytics @unchaindata_xyz

#DataAnalytics #BlockchainData #EIP1559
