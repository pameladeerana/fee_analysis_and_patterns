# Fee Analysis and Patterns

## Description
Simple fee analysis fof the Ethereum Newtwork for the 7-day dataset (Oct 26 - Nov 1, 2026). Explores how ETH moves and how gas fees behaved within the given period. Shows top senders, first wallet activity, EIP-1559 breakdown, rolling gas average, and base fee change between blocks. All values stored in wei and converted to ETH (1 ETH = 1e18 wei).

## 1. Parts / Statements

**1. ETH Value Transferred Per Sender**
Top 10 addresses by total ETH sent in successful transactions in the 7-day dataset. Values in wei converted to ETH. Short address format first 6 + last 4 chars, no 0x.

**2. First Transaction Per Wallet**
Finds the first transaction for each wallet using window functions (ROW_NUMBER). Shows when a wallet first became active in the 7-day period. Uses window functions / window row number.

**3. EIP-1559 Fee Breakdown**
Breakdown of EIP-1559 in past 7 days: base fee + priority fee = total fee by transaction hash, total is sum of both in wei. Breakdown is by transaction hash (tx_hash). Values in wei converted to ETH (1 ETH = 1e18 wei). Base fee reacts to block congestion & is burned, priority fee is for validators.

**4. 3-Block Rolling Average Gas Price**
Calculates 3-block rolling average gas price to smooth spikes. Uses gas and fees / rolling average. Shows significant trend during Oct 29 spike.

**5. Base Fee Change Between Consecutive Blocks**
Daily / block change of base fee between consecutive blocks. Uses window functions / window lag lead. Shows +5.69 gwei spike on Oct 29 after Binance hack, then -4.77 gwei drop on Oct 30.

## 2. Workflow

1. Explored tables on Dune, picked the block range for last 7 days (Oct 26 - Nov 1, 2026).
2. Queried dataset for 5 parts (assisted with WizardsCamp and AI for automation of queries).
3. Made visualizations and built final dashboard.

## 3. Files

- **README.md** - Project overview.
- **Dune Queries and Results**:
  - Part 1 - ETH Value Transferred Per Sender: https://dune.com/queries/9054921
  - Part 2 - First Transaction Per Wallet: https://dune.com/queries/9056625
  - Part 3 - EIP-1559 Fee Breakdown: https://dune.com/queries/9057825
  - Part 4 - 3-Block Rolling Average Gas Price: https://dune.com/queries/9061567
  - Part 5 - Base Fee Change Between Consecutive Days: https://dune.com/queries/9063287
- **Dune Dashboard**: https://dune.com/pameladeerana/fee-analysis-and-patterns

## 4. Data Coverage

- **Snapshot Date:** October 26 - November 1, 2026
- **Blocktime Range:** 2026-10-26 00:00:00 UTC to 2026-11-02 00:00:00 UTC (from query_9055030) 
- **Block Number Range:** 26273137 to 26323364

## 5. Tools

- Dune Analytics
- WizardCamp
- LLM Meta AI

## Author

Pamela Dee Elegio Rana
