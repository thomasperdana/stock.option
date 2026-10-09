# Zero-to-Hero Guide: Selling 30-DTE Puts on Discounted Blue Chips

**What the strategy pays, how to run it well, and a straight answer on the 30%-a-month target.**

*October 2026. Option prices in this guide are Black-Scholes estimates on a $100 stock (30 days to expiration, 4% interest rate, no dividend, no volatility skew). Real quotes will differ somewhat, so check a live option chain before trading.*

> This is general education, not personalized investment advice, and it is not written by a licensed financial adviser. Selling options can lose many times the premium collected. Fit every decision to your own finances, and consider speaking with a licensed professional before committing real money.

---

## Contents

1. [The bottom line first](#1-the-bottom-line-first)
2. [Zero: how selling a put works](#2-zero-how-selling-a-put-works)
3. [The 30%-a-month question](#3-the-30-a-month-question)
4. [Finding the discounted blue chip](#4-finding-the-discounted-blue-chip)
5. [Building the trade](#5-building-the-trade)
6. [Managing the trade](#6-managing-the-trade)
7. [Assignment and the wheel](#7-assignment-and-the-wheel)
8. [Position sizing](#8-position-sizing)
9. [Case studies](#9-case-studies)
10. [Tips and tricks](#10-tips-and-tricks)
11. [Best-practice checklist](#11-best-practice-checklist)
12. [Things to avoid](#12-things-to-avoid)
13. [FAQs](#13-faqs)
14. [A 90-day zero-to-hero plan](#14-a-90-day-zero-to-hero-plan)

Worked examples: **1** basic put (§2) · **2** three kinds of "return" (§3.2) · **3** leverage (§3.3) · **4** the 30% spread (§3.4) · **5** selling into a panic (§5) · **6** closing early (§6) · **7** rolling (§6) · **8** the wheel (§7)

---

## 1. The bottom line first

- **The strategy is sound.** Selling a cash-secured put on a quality company you would be glad to own, at a strike below an already-depressed price, pays you to wait for an even better entry.
- **30% a month is not available from it.** A 30-day put on a blue chip pays roughly 1–3% of the cash securing it in ordinary markets and 3–5% in a panic (§3.1). 30% a month is ten to twenty times that. Compounded, it is about 2,230% a year: $10,000 would become $233,000 in one year, $126 million in three and $68 billion in five.
- **The only way to manufacture the number is leverage.** At the leverage required, an ordinary 10–15% dip in the stock halves the account, and brokers do not even permit the full amount (§3.3).
- **What is realistic:** 1.5–2.5% a month in premium on deployed cash when the setup is good. That is about 20–30% annualized *before* the losing months. Over full market cycles, disciplined put selling has delivered stock-market-like returns with a smoother ride (§3.5).
- **Three "30s" worth aiming at instead:**
  - about 30% *annualized* premium yield on the cash you deploy (≈2.4% a month);
  - about 30% *return on risk* on a small, defined-risk put spread (§3.4);
  - an effective purchase price about 30% below the stock's high (Example 5).

The rest of this guide teaches the version that works, and shows the arithmetic behind every claim above.

---

## 2. Zero: how selling a put works

A **put option** gives its buyer the right to sell 100 shares of a stock at a fixed price (the **strike**) until a fixed date (the **expiration**). When you **sell** a put, you are paid cash up front (the **premium**) and you take on the obligation to buy those 100 shares at the strike if the buyer chooses.

**Cash-secured** means you keep the full purchase price (strike × 100) in the account. Nothing is borrowed. The worst case is that you own a stock you chose, at a price you chose.

There are only two outcomes at expiration:

| Stock finishes | What happens | Result |
|---|---|---|
| Above the strike | The put expires worthless | You keep the premium |
| Below the strike | You are **assigned**: you buy 100 shares at the strike | You own the stock at strike − premium |

### Vocabulary

| Term | Meaning |
|---|---|
| Strike | Price at which you agree to buy the shares |
| Premium (credit) | Cash you receive for selling the put, quoted per share (× 100 per contract) |
| DTE | Days to expiration. "30 DTE" means the option expires in 30 days |
| Assignment | Being required to buy the shares. Possible any time on US stock options, usual only at expiration |
| Breakeven | Strike − premium. Below this price you are losing money |
| Delta (Δ) | How much the option moves per $1 move in the stock. Also a rough gauge of the chance the put finishes in the money: a 0.30Δ put has about a 30–35% chance |
| Theta | Value the option loses per day from the passage of time. This is what the seller earns |
| Implied volatility (IV) | The market's forecast of how much the stock will move, expressed as an annual %. Higher IV means higher premiums |
| IV rank | Where today's IV sits in its 52-week range: (IV − low) ÷ (high − low). 80 means IV is near its yearly high |
| OTM / ATM / ITM | Out of, at, or in the money. For a put: strike below, at, or above the stock price |
| Extrinsic value | The part of the premium that is pure time and volatility value |
| Buying power reduction | Collateral your broker locks up for the trade |

### The formulas you will use every day

```
Return on cash      = premium ÷ strike
Annualized return   = return on cash × 365 ÷ days held
Breakeven           = strike − premium
Discount to price   = (stock price − breakeven) ÷ stock price
Expected 1-SD move  = stock price × IV × √(DTE ÷ 365)
Return on risk      = credit ÷ (spread width − credit)        (spreads only)
```

### Example 1: the basic cash-secured put

XYZ is a blue chip that has fallen from $125 to $100. Its IV has risen to 40%. You would be happy to own it in the low $90s.

- **Trade:** sell 1 XYZ put, $95 strike, 30 DTE, for $2.30 (about 0.30Δ)
- **Cash set aside:** $9,500
- **Premium received:** $230 → **2.4% for the month** (about 29% annualized)
- **Breakeven:** $92.70, which is 7.3% below today's price and 26% below the $125 high

| XYZ at expiration | Put seller | Someone who bought 100 shares at $100 |
|---|---|---|
| $105 | +$230 | +$500 |
| $100 | +$230 | $0 |
| $95 | +$230 | −$500 |
| $92.70 | $0 (own shares at breakeven) | −$730 |
| $90 | −$270 | −$1,000 |
| $80 | −$1,270 | −$2,000 |
| $70 | −$2,270 | −$3,000 |

Two things to take from the table:

1. On the downside the put seller is always $730 better off than the share buyer. That cushion is the whole benefit.
2. The gain is capped at $230 no matter how far the stock rallies, and the loss is not capped until the stock hits zero. **You are being paid a small, fixed amount to carry most of the stock's downside.** Everything else in this guide follows from that asymmetry.

---

## 3. The 30%-a-month question

### 3.1 What a 30-day put pays

Premium as a percentage of the cash securing the put, for one 30-day cycle:

| Implied volatility | Typical of | 0.16Δ put (about 1 SD out) | 0.30Δ put | At-the-money put |
|---|---|---|---|---|
| 20% | Calm staple or utility | Strike 5% below price → **0.5%** | 2.5% below → **1.2%** | **2.1%** |
| 30% | Typical large cap | 8% below → **0.8%** | 4% below → **1.8%** | **3.3%** |
| 40% | Stock under pressure | 10% below → **1.1%** | 5% below → **2.4%** | **4.4%** |
| 60% | Market panic or company crisis | 14% below → **1.8%** | 7% below → **3.9%** | **6.7%** |
| 80% | Existential event | 18% below → **2.6%** | 9% below → **5.4%** | **9.0%** |

Reading it:

- Most blue chips trade at 20–35% IV most of the time. A sensible put pays **about 1–2% a month**.
- A discounted blue chip, sold off with IV at 40–60%, pays **about 2.5–4%**.
- Even selling at the money on a stock priced for catastrophe pays 9%.
- An at-the-money 30-day put pays 30% of its strike only when IV is around **270%**. That is a small biotech the night before an FDA ruling. Nothing that deserves the name blue chip trades there.

### 3.2 Three different things people call "return"

Most claims of "30% a month" use a different denominator from the one you care about.

**Example 2.** A $100 stock with 30% IV. You sell the 30-day $96 put for $1.63.

| How it is financed | Capital tied up | "Return" for the month |
|---|---|---|
| Cash-secured | $9,600 | $163 ÷ $9,600 = **1.7%** (return on cash) |
| On margin (naked put) | About $1,600 | $163 ÷ $1,600 = **10%** (return on margin) |
| As a spread, buying the $91 put for protection | $389 at risk for a $111 credit | $111 ÷ $389 = **28%** (return on risk) |

It is the same short put each time. The risk did not shrink; the denominator did. With margin you still lose a dollar per share for every dollar the stock falls below $94.37, now against a sixth of the capital. With the spread the loss is capped, but losing the entire $389 happens roughly one time in seven.

Other sources of big numbers: annualized returns quoted as if they were monthly, a single hand-picked winning trade, and options on speculative stocks relabeled as "quality."

### 3.3 What 30% a month would take: leverage

Using the 0.30Δ put on a 30%-IV stock (1.8% for the month, strike 3.7% below the price), here is what happens as you sell more puts than you have cash to cover:

| Notional ÷ account | Best-case month | Stock decline that costs half the account | Stock decline that wipes it out |
|---|---|---|---|
| 1× (cash-secured) | +1.8% | −54% | Cannot happen |
| 2× | +3.6% | −30% | −54% |
| 3× | +5.3% | −22% | −38% |
| 5× | +8.9% | −15% | −25% |
| 7× | +12.5% | −12% | −19% |
| 17× (what 30% needs) | +30% | −8% | −11% |

For scale: a normal one-standard-deviation month for a 30%-IV stock is ±8.6%. At 17× an ordinary month ends the account. No broker offers 17× anyway; standard margin stops at roughly 5–6× for near-the-money puts.

**Example 3: reaching for just 8% a month.** A $50,000 account sells 25 contracts of the $96 put above across several stocks for $1.63 each. Premium: $4,075, an 8.2% month if all goes well. Notional exposure: $240,000, or 4.8× the account.

| Stocks at expiration | Profit / loss | Account |
|---|---|---|
| −4% ($96) or higher | +$4,075 | +8% |
| −8% ($92) | −$5,925 | −12% |
| −10% ($90) | −$10,925 | −22% |
| −15% ($85) | −$23,425 | −47% |
| −20% ($80) | −$35,925 | −72% |

It rarely reaches expiration. Suppose the stocks drop 12% in the first ten days and IV jumps to 55%. The puts are now worth about $9.60. Account equity is about $30,000, the margin requirement has risen to about $44,000, and the broker liquidates the positions at the worst prices of the month. A paper loss becomes a permanent 40% loss, and the account is not there for the rebound.

That is the cost of an 8% target. A 30% target is the same picture with the fuse cut to a third of the length.

### 3.4 The spread version: 30% return on risk

A **put credit spread** sells one put and buys a lower-strike put as insurance. The maximum loss is fixed, so the capital required is small and the percentage return looks large.

**Example 4.** $100 stock, 40% IV, 30 DTE. Sell the $94 put, buy the $89 put.

- Net credit: **$1.14** ($114 per spread)
- Maximum loss: $5.00 − $1.14 = **$3.86** ($386)
- Return on risk: $114 ÷ $386 = **29.7%**

Here is a genuine 30% in 30 days. Now the odds:

| Outcome at expiration | Approximate probability | Result |
|---|---|---|
| Stock above $94 | 70% | +$114 |
| Stock between $89 and $94 | 14% | Partial, averaging about −$136 |
| Stock below $89 | 16% | −$386 |

Over 100 such trades: 70 × $114 − 14 × $136 − 16 × $386 ≈ **−$100**. Essentially zero, before commissions. That is not a coincidence. Option prices are set so that the premium roughly equals the expected loss. (Real markets also charge more for the lower put than this model assumes, so actual credits run a little thinner.)

A seller's real edge comes from two places, and both are modest:

1. **The volatility risk premium.** Implied volatility has, on average, run somewhat above what stocks then actually delivered. Sellers of insurance earn a margin over time.
2. **Selection.** Selling only on quality companies after an overreaction, where the true odds are better than the market's.

"30% on risk" becomes an account return only through sizing. Risk 3% of the account on each of five spreads and the best-case month is about +4.5% on the account, while a broad selloff that takes out all five costs 15%. Risk the whole account to "make 30%" and the first bad month, which the table says arrives about one month in six, takes everything.

### 3.5 What long-run put selling has earned

The cleanest long record is the **Cboe S&P 500 PutWrite Index (PUT)**. Each month it sells a one-month, at-the-money S&P 500 put, fully secured by Treasury bills. Published studies of its history from 1986 put the compound return at roughly **9–10% a year**: close to the S&P 500 itself, with about two-thirds of the volatility. It collected very roughly 1.5–2% a month in premium to get there, kept perhaps a third to a half of it after losing months, and still lost about a third of its value in 2008. (Figures approximate.)

So the most systematic, diversified form of this trade has earned about 0.8% a month over decades. Good stock selection and timing can add to that. They cannot multiply it by thirty.

### 3.6 Targets worth aiming at

| Style | Setup | Premium for the month, on cash | Finishes below the strike |
|---|---|---|---|
| Conservative | 0.15–0.20Δ, IV 25–35% | 0.7–1.2% | About 1 time in 5 |
| Standard | 0.25–0.30Δ, IV 30–40% | 1.5–2.5% | About 1 time in 3 |
| Opportunistic | 0.20–0.30Δ, IV 50%+ after a selloff | 2.5–4% | About 1 time in 3–4 |

These are the good months. A plain picture of both kinds, for a $50,000 account running five $10,000 positions at about 2%:

- **Clean month:** all five expire. +$1,000, or +2%.
- **Rough month:** the market drops 10%. Two puts expire (+$400). Three finish 7% below their breakevens (−$2,100). Net −$1,700, or −3.4%, and you now own three stocks to work back with covered calls.

A year that mixes the two honestly lands in the range of a good stock-market year, with shallower dips. That is the prize. It is a real one.

How monthly rates compound, for calibration:

| Monthly | Yearly | $10,000 after 3 years |
|---|---|---|
| 1% | 12.7% | $14,300 |
| 2% | 26.8% | $20,400 |
| 3% | 42.6% | $29,000 |
| 30% | 2,230% | $126,000,000 |

---

## 4. Finding the discounted blue chip

Stock selection matters more than option selection. A mediocre strike on a great company recovers. A perfect strike on a deteriorating one does not.

### 4.1 Is it a blue chip?

| Test | Threshold |
|---|---|
| Size | Market cap above roughly $50B; S&P 500 or Dow member |
| Profitability | Positive free cash flow every year through at least one recession |
| Balance sheet | Investment-grade credit, ideally A-range; net debt under about 3× EBITDA (for banks and insurers, strong capital ratios instead) |
| Moat | Stable or rising market share; returns on capital consistently above 10–12% |
| Shareholder record | Dividend and buybacks maintained through the last downturn |
| Options market | Monthly open interest in the thousands, bid-ask a few cents wide |

Blue chip is a description of the past, not a guarantee. General Motors was in the Dow for more than 80 years before its 2009 bankruptcy. General Electric fell more than 80% in 2008–09, Citigroup about 98%.

### 4.2 Is it discounted?

Look for at least two of these:

- **Price:** 15–30% or more below its 52-week high.
- **Valuation:** forward P/E, price-to-free-cash-flow, or EV/EBITDA at least 15–20% below the stock's own 5–10 year median, *with earnings estimates holding up*.
- **Yield:** free-cash-flow yield or dividend yield near the top of its historical range, with the dividend covered by cash flow.
- **Chart:** holding a long-term support zone, selling volume fading, RSI turning up from below 30.

A stock that is down 40% because its earnings fell 40% is not discounted. It is repriced.

### 4.3 Why is it down?

This is the question that separates a discount from a value trap.

| Usually temporary: candidates | Often structural: pass |
|---|---|
| Broad market selloff or macro scare | Revenue shrinking for several quarters, market share lost |
| Sector rotation, interest-rate fears | Core product or business model being displaced |
| One-off earnings miss with guidance intact | Guidance withdrawn, senior management leaving |
| Legal or regulatory headline with a bounded cost | Accounting questions, criminal probes, open-ended liability |
| Temporary margin pressure (input costs, currency) | Dividend cut or at risk; debt rising to fund capex or buybacks |

If you cannot explain in two sentences why the stock fell and why that reason will fade within a year or two, skip it.

### 4.4 Build the watchlist before you need it

Keep 15–25 companies that pass §4.1, spread across at least five sectors. Next to each, write the price at which you would be genuinely pleased to own it. Then wait. The trade is on when the market brings a name to your price with elevated IV, not when you feel like collecting premium.

---

## 5. Building the trade

| Decision | Guideline | Why |
|---|---|---|
| Expiration | 30–35 DTE at entry (25–45 is acceptable), monthly cycle | Best balance of time decay against sudden-move risk; deepest liquidity |
| Strike | 0.20–0.30Δ as standard; 0.15–0.20Δ after a crash or for your first trades | Roughly 65–80% chance of expiring worthless |
| Strike sanity check | At or below your "pleased to own" price, and below a visible support level | The strike is a purchase price, not just a number on a chain |
| IV rank | Above 30, ideally above 50 | You are selling insurance; sell it when it is expensive |
| Minimum premium | At least 1% of the strike for the month | Below that, the reward does not pay for the tail risk |
| Earnings | Expiration before the next report, or enter the day after it | Earnings gaps are the most common cause of large losses |
| Liquidity | Open interest of 500+ at the strike; bid-ask within about 5% of the option's price | Wide spreads quietly eat the edge |
| Size | Collateral of no more than 5–10% of the account per position (§8) | Survive being wrong |

### Example 5: selling into a panic

XYZ has dropped from $135 to $100 in three weeks during a market-wide selloff. Business fundamentals are unchanged. IV is 55%, at the top of its yearly range.

| Strike | Delta | Premium | Return on cash, 30 days | Breakeven | Breakeven vs. $135 high |
|---|---|---|---|---|---|
| $95 | 0.34 | $3.82 | 4.0% | $91.18 | −32% |
| $92.50 | 0.28 | $2.92 | 3.2% | $89.58 | −34% |
| $90 | 0.22 | $2.17 | 2.4% | $87.83 | −35% |
| $85 | 0.13 | $1.09 | 1.3% | $83.91 | −38% |

The $90 put is the strategy at its best: paid 2.4% for one month (about 29% annualized) to agree to buy a quality business 35% below its recent high, with only about a one-in-four chance of being assigned. In a panic, choose the further strike and the smaller size. The premium already compensates you for distance, and the gap risk is at its highest.

### Placing the order

1. Confirm there is no earnings report before expiration.
2. Pick the monthly expiration closest to 30 days.
3. Pick the strike using delta, your target price and support.
4. Calculate return on cash and breakeven. If the return is under 1% or the breakeven is not a price you want, stop.
5. Enter **Sell to Open**, 1 contract, **limit** order at the midpoint of bid and ask. If unfilled after a few minutes, lower by a few cents at a time. Never use a market order.
6. Once filled, immediately enter a good-till-cancelled **Buy to Close** order at half the credit received.
7. Set a calendar reminder for 7–10 days before expiration.
8. Log the trade (§10, tip 12).

---

## 6. Managing the trade

**Rule 1: take profits at 50%.** An out-of-the-money put that is working often loses half its value in the first third to half of its life. The second half of the premium takes longer to earn and carries most of the risk.

**Example 6.** Ten days after the trade in Example 1, XYZ has drifted to about $101 and IV has eased. The put is worth about $1.15. Your resting order fills: +$115 in 10 days, 1.2% on $9,500, with the cash freed for the next setup. Waiting 20 more days for the other $115 means holding all of the downside for half the pay.

**Rule 2: do not sit through the final week close to the strike.** At 7 DTE, close or roll anything within about 3% of its strike. Far out-of-the-money puts can be left to expire.

**Rule 3: when the position is tested, follow the tree.**

```
Stock at or below the strike with 10 or fewer days left.
Is the reason you wanted to own this company still true?
├─ No  → Buy to close. Take the loss. Do not roll.
└─ Yes → Do you want the shares at this cost, within your position-size cap?
        ├─ Yes        → Take assignment and move to Section 7.
        └─ Would rather wait → Roll out about 30 days, same or lower strike,
                               only for a net credit.
                               No credit available → take assignment or close.
```

**Example 7: rolling.** Seven days left on the Example 1 put. XYZ is at $93 and IV is 45%. The $95 put now costs $3.42 to buy back.

| Choice | Action | Net credit | Total credit | New breakeven |
|---|---|---|---|---|
| Take assignment | Buy 100 shares at $95 | — | $2.30 | $92.70 |
| Roll out | Buy back the $95, sell the 37-DTE $95 at $6.20 | $2.78 | $5.08 | $89.92 |
| Roll down and out | Buy back the $95, sell the 37-DTE $92.50 at $4.86 | $1.44 | $3.74 | $88.76 |
| Roll further down and out | Buy back the $95, sell the 37-DTE $90 at $3.70 | $0.28 | $2.58 | $87.42 |

Rolling down and out for a credit lowers the purchase price and buys time. It also keeps capital in a losing position for another month. Roll once or twice on a company you still believe in. Beyond that you are avoiding a decision.

**Rule 4: the thesis is the stop-loss.** For a cash-secured put on a company you want to own, a lower price alone is not a reason to exit. A dividend cut, withdrawn guidance, or an accounting question is. When the reason changes, close without negotiating.

**Rule 5: do not turn winners into risk.** When a put is up 50%, close it. Do not roll it up to a higher strike to squeeze out more premium.

---

## 7. Assignment and the wheel

Assignment is not a failure. It is the second half of the plan: you now own the stock at strike minus premium. The **wheel** continues by selling covered calls against the shares until they are called away, then returning to puts.

**Example 8.**

| Month | Action | Premium | Running cost basis |
|---|---|---|---|
| 1 | Sell the $95 put. XYZ finishes at $90; assigned at $95 | $2.30 | $92.70 |
| 2 | Sell the 30-DTE $95 call. XYZ finishes at $94; call expires | $2.30 | $90.40 |
| 3 | Sell the 30-DTE $97.50 call. XYZ finishes at $99; shares called away at $97.50 | $2.45 | $87.95 |

Result: $7.05 in premium plus $2.50 of stock gain = **$955 on $9,500 in three months**, about 10%. A buyer of shares at $100 on day one is down 1%.

Now the other branch. If XYZ slides to $75 instead, a call at your $92.70 cost basis pays almost nothing, and the premium collected covers only a small part of a $20-per-share loss. **The wheel softens a decline. It does not prevent one.**

Covered-call rules after assignment:

- Sell calls at or above your cost basis, 30 DTE, around 0.20–0.30Δ.
- Do not sell calls below your cost basis unless you have decided to exit at a loss. A sharp rebound would take your shares away just as the recovery begins.
- Immediately after a crash, wait before selling calls. Rebounds from panic lows are fast, and call premium rarely pays enough to give them up.
- If the company's story has broken, sell the shares. Selling calls on a stock you no longer want is still owning it.

---

## 8. Position sizing

Sizing is what decides whether a bad trade is a setback or the end. Hold these as rules.

1. **No leverage.** Total notional (strike × 100 × contracts, summed over all positions) stays at or below the account value. A margin account will let you exceed this. Police it yourself.
2. **Cap each company.** No more than 5–10% of the account as collateral on one name. Smaller accounts must accept more concentration and should compensate with fewer, higher-quality positions.
3. **Cap each sector** at about 25%. In a selloff, stocks in one sector fall together.
4. **Hold a reserve.** Uncommitted cash lets you act when premiums are richest.
5. **Ladder entries.** One new position a week spreads out both entry prices and expirations.
6. **Stress-test monthly.** Assume every stock you are short puts on falls 25% in a month. Add up the loss. If it exceeds what you can stand (many use 15–20% of the account), reduce.

A rule of thumb for how much cash to commit, by market volatility:

| VIX | Share of account committed to puts | Reasoning |
|---|---|---|
| Below 15 | 30–50% | Premiums are thin; be selective |
| 15–25 | 50–70% | Normal conditions |
| 25–35 | 70–85% | Premiums are rich; lean in |
| Above 35 | Toward 100%, added in thirds over several weeks | Best prices, and the highest chance of further falls |

What fits, by account size:

| Account | Practical approach |
|---|---|
| Under $10,000 | One contract needs strike × 100 in cash, which rules out most blue chips. Buy shares or an index fund while building capital, or run one small put spread at a time with no more than 3–5% of the account at risk. |
| $10,000–$25,000 | One to three cash-secured puts on quality stocks priced roughly $30–$80. Concentration is unavoidable, so be strict on quality. |
| $25,000–$100,000 | Four to eight positions at 10–15% each across different sectors. |
| Above $100,000 | Ten to twenty positions at 5% each, with the sector cap enforced. |

---

## 9. Case studies

*Prices and dates are approximate. Verify against a chart before quoting them.*

### Case 1: Meta, 2022. One company, two outcomes

- **February 2022.** The stock falls 26% in a day to about $237 after its first decline in daily users. A dominant franchise at about 17 times earnings looks like a discounted blue chip.
- **Seller A** sells a 30-day $210 put the following week and is assigned in March. By early November the stock is near $90, 57% below the strike. It does not trade back above $210 until spring 2023, more than a year later.
- **Seller B** waits and sells puts after the next collapse in late October 2022, when the stock drops another 25% to about $98. Strikes in the $85–$90 range expire worthless. The stock ends the year near $120 and is above $180 by early February 2023.

**Lessons.** A 26% drop is not a floor. Both sellers were right about the business; Seller A survived being early only if the position was small. And a wheel trader who "repaired" the position by selling covered calls around $115 in January 2023 would have had the shares called away at that price, missing a 23% one-day jump in early February and the recovery that followed.

### Case 2: Intel, 2024. The value trap

- About $50 at the end of 2023 and in the low $30s by July 2024. It looked cheap, paid a dividend and was treated as a strategic national asset.
- August 2024 earnings: dividend suspended, 15% of the workforce cut. The stock fell 26% the next day to about $21.50. In November it was removed from the Dow.
- A seller of $30 puts that spanned the earnings date was assigned with the stock near $20: down a third within weeks. Covered calls at $30 paid pennies. The stock stayed near $20 for about a year, and the eventual recovery followed outside investments that no screen could have predicted.

**Lessons.** Shrinking revenue, lost market share and capital spending beyond cash flow are structural, not a discount. A dividend is not a floor. Never hold a short put through earnings by accident.

### Case 3: Boeing, 2019–20. The tail arrives late

- About $440 before the 737 MAX grounding in March 2019. For the rest of the year it held between roughly $320 and $390. Half of a global duopoly, a Dow member, a favorite for buying dips. Puts at $300 paid well and expired worthless month after month.
- February to March 2020: from about $340 to under $100 in five weeks. The dividend was suspended.
- A $300 put became a $200-per-share loss at the low. At 5% of an account, that is a 3–4% dent. Concentrated at 3× leverage, it is the whole account.

**Lessons.** A long run of wins says nothing about the tail. A company already impaired (a grounded product, rising debt) is fragile to a second shock. The position cap is what made this survivable.

### Case 4: March 2020. Same trades, different financing

- The S&P 500 fell 34% in 23 trading days. The VIX set a record close near 83.
- **Cash-secured sellers** were assigned across the board, carried paper losses of 20–35%, sold calls, and saw the index back at a record by August.
- **Margin sellers at 3–5×** were liquidated near the lows as requirements expanded. Paper losses became permanent ones.
- This was not new. A mutual fund that sold S&P options with leverage lost about 80% in two days in February 2018, and a well-known option-selling advisory firm wiped out its clients' accounts in a single week that November.

**Lesson.** Survival is the strategy. Both groups made the same trades. Only one was still in the market for the recovery.

### Case 5: April 2025. When premium is truly rich

- After the tariff announcement on April 2, the S&P 500 fell about 12% in four sessions and the VIX closed above 50. Implied volatility on the strongest large caps roughly doubled for several days.
- At that kind of IV, a 30-DTE put 10% below the price pays about 2.4% for the month (Example 5).
- A policy pause on April 9 produced a 9.5% one-day rally. The index was at a record by late June. Puts sold in the panic expired worthless.

**Lessons.** This is the setup the strategy waits for. Still, scale in by thirds. In September 2008 the same trade was assigned and then fell another 30–40% over the next five months. Premium was high both times, and only hindsight tells you which year you are in.

### Case 6: UnitedHealth, 2025. The discount that kept discounting

- About $630 in November 2024. In April 2025 a guidance cut took 22% off in a day, to about $450. In May the CEO left and guidance was withdrawn: down another 18%, to about $310. Days later a report of a federal investigation pushed it briefly near $250.
- Each step looked like capitulation. A seller of $400 puts after the April drop, a strike 12% below the price, was assigned and down about 35% within a month. The stock recovered part of the loss later in the year.

**Lessons.** When the cause is of unknown size (guidance withdrawn, an investigation, a management exit), the discount cannot be measured. Wait for the company to restate its outlook. At 5% of the account, this trade cost under 2%.

---

## 10. Tips and tricks

1. **Sell on red days.** Put premium is richest when the stock is down and IV is up. The same strike can pay 20–40% more than on a green day.
2. **Enter the 50% buy-to-close order the minute you are filled.** It takes the exit decision out of your hands.
3. **Put the strike under something:** a prior low, the 200-day average, a gap, a round number.
4. **Use the expected move as a ruler.** Price × IV × √(DTE ÷ 365). At 30% IV that is ±8.6% over 30 days. A strike inside that range will be tested often.
5. **Ladder.** One position a week instead of five in a day.
6. **Earn interest on the collateral.** Many brokers accept Treasury bills or a money-market fund as security for the put. That yield is added to the premium.
7. **Compare the put with a limit order.** If you would happily buy at $95, the put pays you to wait. If you believe the stock is about to run, buy shares; the put caps you at the premium.
8. **Prefer monthly expirations** (third Friday). They have the most liquidity and the tightest spreads.
9. **Work the order.** On a $1.50 option, giving up $0.10 is 7% of the profit.
10. **When nothing qualifies, sell nothing,** or sell a put on a broad index ETF. An index cannot have an earnings disaster.
11. **Know the index-option alternative.** Options on the S&P 500 index itself (SPX, XSP) are cash-settled, cannot be assigned early, and in US taxable accounts receive 60% long-term / 40% short-term treatment.
12. **Keep a journal:** date, stock price, IV rank, delta, DTE, credit, exit price, days held, reason for the trade. After 30 trades you will know your own win rate and average loss, which is worth more than any rule here.
13. **After a crash, go further out** (0.15–0.20Δ). The premium already pays for the distance.
14. **Check the calendar every time:** earnings, investor days, court and regulatory rulings, central-bank meetings.
15. **Judge yourself on account return and drawdown** against simply holding an index fund. Win rate alone says little.

---

## 11. Best-practice checklist

**Before the trade**

- [ ] The company passes the blue-chip test (§4.1)
- [ ] It is discounted on at least two measures (§4.2)
- [ ] I can state why it fell and why that is temporary (§4.3)
- [ ] I would be content to own it for two years at the breakeven price
- [ ] No earnings report before expiration
- [ ] IV rank above 30
- [ ] 25–45 DTE, monthly expiration
- [ ] Delta between 0.15 and 0.30
- [ ] Premium at least 1% of the strike
- [ ] Open interest and bid-ask spread acceptable
- [ ] Position within 5–10% of the account; sector within 25%
- [ ] Total notional at or below account value

**During the trade**

- [ ] 50% buy-to-close order resting
- [ ] Reminder set for 7–10 DTE
- [ ] News checked weekly for anything that changes the thesis
- [ ] If tested, decision tree followed (§6)

**After the trade**

- [ ] Journal updated
- [ ] If assigned, covered call sold at or above cost basis (§7)
- [ ] Monthly: stress test run, results compared with an index benchmark

---

## 12. Things to avoid

1. **Sizing to a return target.** Deciding you need 30%, or even 5%, this month and working backward to a contract count is how accounts end. Size from risk and accept the return the market is offering.
2. **Leverage.** Selling more puts than you have cash to cover turns a survivable drawdown into a liquidation (Example 3).
3. **Chasing premium.** Sorting the chain by highest yield leads straight to the most dangerous stocks. High IV is a warning label before it is an opportunity.
4. **Selling puts on companies you do not want to own.**
5. **Holding through earnings by accident.**
6. **Concentration** in one company or one sector.
7. **Catching the first day of a collapse.** Let the stock trade for several sessions and let management speak.
8. **Mistaking a price drop for a discount** (§4.2).
9. **Rolling indefinitely** to avoid ever booking a loss.
10. **Selling covered calls below your cost basis** after assignment.
11. **Going all in at the first volatility spike.**
12. **Doubling down** with more puts on the same falling name beyond your cap.
13. **Market orders and illiquid chains.**
14. **Spending premium before the trade is closed.** It is not income until then.
15. **Switching to weekly or same-day options to "compound faster."** More trades, more sudden-move risk, less room to be wrong.
16. **Paying for a system that advertises 30% a month.** Ask which denominator is being used (§3.2) and ask for audited, account-level results over several years.
17. **Ignoring taxes.** In a US taxable account, option premium is generally a short-term gain.

---

## 13. FAQs

**Can any put-selling approach produce 30% a month?**
Not on the account, and not repeatedly. A single trade can show 30% on margin or on risk (§3.2), and a lucky month at high leverage can show it on the account. Repeated monthly, the leverage required makes a wipeout a matter of time.

**Then what should I expect?**
In good months, 1.5–2.5% on the cash deployed. Over full cycles, something like a solid stock-market return with smaller swings, and stock-like losses in a crash (§3.5).

**How much capital do I need?**
Strike × 100 per contract. A $60 stock needs $6,000; a $250 stock needs $25,000. See the table in §8.

**What broker approval is required?**
Cash-secured puts usually need only a basic options level and are commonly allowed in retirement accounts. Spreads need a higher level. Selling puts on margin needs the highest, and is the one to avoid.

**Why 30 DTE rather than weeklies or 60 days?**
Thirty to forty-five days is where daily time decay is meaningful but one bad day does not decide the trade. Weeklies show higher annualized numbers on paper with far less margin for error. Longer dates tie up capital for slower decay.

**Which delta?**
0.20–0.30 for most trades. Go to 0.15–0.20 when you are starting out or selling into a panic.

**What happens if I am assigned? Can it happen early?**
You buy 100 shares at the strike and keep the premium. Early assignment is possible on stock options and is rare unless the put is deep in the money with almost no time value left. If it happens, you simply own the shares sooner.

**Should I always take assignment?**
Only when the thesis is intact and the position fits your size cap. Otherwise close (§6).

**Is selling puts better than buying the stock?**
It does better when the stock is flat, slightly down or slightly up. It does worse in strong rallies, because your gain is capped. The PutWrite Index has trailed the S&P 500 noticeably through the powerful bull runs of the past decade.

**What happens in a crash?**
You are assigned on most positions and carry losses a little smaller than a shareholder's. Unleveraged, you can hold and sell calls. That is why rule 1 of §8 exists.

**Cash-secured puts or put credit spreads?**
Cash-secured puts fit the goal of owning good companies cheaply. Spreads use far less capital and cap the loss, but they lose their entire stake fairly often, and you do not end up owning the stock. If you use them, risk 1–3% of the account per spread and keep total spread risk under about 15%.

**Should I ever use margin?**
The safe default is no. Keep collateral in cash or Treasury bills.

**How do I find candidates?**
Screen for large-cap stocks down 15% or more from their highs, then apply §4 by hand. Most charting and broker platforms show IV rank. The watchlist in §4.4 does most of the work.

**How is it taxed in the US?**
Generally: premium on a put that expires or is bought back is a short-term capital gain or loss. If you are assigned, the premium reduces the cost basis of the shares. Broad-index options follow the 60/40 rule. Wash-sale rules can apply. Confirm with a tax professional.

**What win rate should I expect?**
Around 70% at 0.30Δ held to expiration, and above 80% when taking profits at 50%, with smaller wins. Win rate is not the measure. One loss can be five to ten times an average win, so track expectancy and drawdown.

**Is the wheel a system that cannot lose?**
No. It loses whenever the stock falls by more than the premium collected (Example 8). It is a disciplined way of owning stocks with some extra income, nothing more.

---

## 14. A 90-day zero-to-hero plan

**Days 1–14: Zero**
- Work through §2 until you can state the breakeven and maximum loss of any put from memory.
- Open a paper-trading account.
- Build the watchlist of 15–20 companies with a "pleased to own" price for each (§4.4).
- Paper-trade five puts using the checklist in §11.

**Days 15–45: First live trades**
- One contract on your best setup (or one small spread if the account is small).
- Rest the 50% exit order. Journal the trade.
- No second position until you have closed the first and reviewed it.

**Days 46–90: Running a book**
- Build to three to five laddered positions across different sectors.
- Handle your first tested position with the decision tree, and your first assignment with a covered call.
- Run the 25% stress test at each month-end.

**Beyond: Hero**
- Thirty or more logged trades.
- Deployment scaled to volatility (§8).
- Index puts added for periods when no single stock qualifies.
- Optionally, a small spread sleeve under the limits in the FAQ.

**The scorecard that matters**

| Measure | What good looks like |
|---|---|
| Account return, annualized | Competitive with an index fund over a full year |
| Maximum drawdown | Shallower than the index over the same period |
| Premium kept ÷ premium collected | Above about 40% |
| Average loss ÷ average win | Known, and stable |
| Largest single-company loss | Under 3–5% of the account |
| Rule breaks | Zero |

The skill in this strategy lies in refusing the trades that pay too much. Take what the market offers on companies you want to own, stay unleveraged, and let the months add up.
