# REMMR — Rade Engine Matchmaking Rating

**Chart Raiders · Rade Engine Module · The First Objective Trading Skill Rating System**

REMMR is the first competitive skill rating system built specifically for financial markets. It powers the Chart Raiders leaderboard and rank progression system — ranking players on actual trading performance, not self-reported results.

---

## What REMMR Is

Every competitive platform needs an honest way to answer: *how good are you, really?*

Traditional brokers have no answer. Esports platforms like Riot and Chess.com have excellent rating systems, but none were built for the unique challenges of competitive trading: high variance, market randomness, session-to-session inconsistency, and match sizes ranging from 2 to 1,000+ players.

REMMR is built from the ground up for this environment. It measures where you finish relative to your competition — not how much money you made — which means good strategy is rewarded even when market conditions work against you.

---

## Game of Skill Foundation

REMMR exists because Chart Raiders is a Game of Skill. The rating system reflects this in every design decision:

**Percentile scoring over raw profit** — finishing 3rd out of 100 reflects your skill level regardless of whether the market gave you a great session or a difficult one. This removes market randomness as a factor in how you are rated.

**Cosmetic-only rankings** — REMMR is for leaderboards and end-of-season rewards. It does not affect matchmaking. Lobbies remain random. This ensures that every player — regardless of rating — always has a real chance at a competitive result. Skill determines who rises over time.

**Player decisions as the intervening variable** — your REMMR score reflects the aggregate of your trading decisions across many matches. It is not a function of any single market movement or any single security's performance.

---

## Scoring Methodology

REMMR uses a **six-criteria weighted methodology**:

| Criteria | Weight | REMMR Score |
|---|---|---|
| Skill measurement accuracy | 25% | 9/10 |
| Variance management | 20% | 9/10 |
| Player experience (all levels) | 20% | 9/10 |
| Anti-manipulation resilience | 15% | 9/10 |
| Engagement architecture | 10% | 8/10 |
| Technical robustness | 10% | 10/10 |
| **Weighted Total** | | **9.0 / 10** |

**Competitive comparison:**

| System | Platform | Weighted Score |
|---|---|---|
| **REMMR** | **Chart Raiders DayTradeSport** | **9.0 / 10** |
| Glicko-2 | Chess.com | 8.1 / 10 |
| LP System | Riot Games (LoL / Valorant) | 7.5 / 10 |
| Matchmaking Rating | Steam | 6.6 / 10 |
| Contest Ranking | DraftKings | 5.4 / 10 |
| P&L Ranking | Traditional Brokers | 2.2 / 10 |

Chess.com's Glicko-2 is the most accurate skill-measurement system in existence — but it scores lower on player experience and engagement. REMMR leads because it combines strong skill accuracy with variance protection and player experience features specifically designed for a competitive trading environment.

---

## How Performance Is Measured

REMMR uses **percentile scoring**:

```
Percentile Score = (Total Entrants − Your Rank) ÷ (Total Entrants − 1)
```

- 1st place = 1.0 (100th percentile)
- Last place = 0.0 (0th percentile)
- Performance delta = Percentile Score − 0.5

**Why percentile instead of profit?** Because market conditions affect everyone equally in a given match. Finishing 3rd out of 100 demonstrates skill regardless of absolute profit. Raw profit scoring would reward lucky sessions and punish skilled players in difficult market conditions. Percentile removes that noise.

---

## Match Size Scaling

```
Match Size Multiplier = log₁₀(Total Entrants)
```

| Match Size | Multiplier |
|---|---|
| 10 players | 1.0× |
| 100 players | 2.0× |
| 1,000 players | 3.0× |

Winning a larger match should be worth more — but the log scale prevents large matches from being overwhelmingly dominant over smaller ones.

---

## Bonuses

**Placement Bonuses:**
| Achievement | Requirement | Bonus |
|---|---|---|
| First Place | Any match | +10 MMR |
| Top 1 in 100+ | 100+ entrants | +15 MMR |
| Top 1 in 500+ | 500+ entrants | +30 MMR |
| Top 1 in 1,000 | 1,000 entrants | +50 MMR |

**Profit Bonuses:**
| Achievement | Profit Required | Bonus |
|---|---|---|
| Legendary Trader 🌟 | 300%+ ($400+) | +25 MMR |
| Master Trader 💫 | 200%+ ($300+) | +15 MMR |
| Expert Trader ✨ | 150%+ ($250+) | +10 MMR |
| Skilled Trader 📈 | 100%+ ($200+) | +5 MMR |
| Solid Gains 💹 | 50%+ ($150+) | +2 MMR |

**Special Bonuses:**
| Achievement | Condition | Bonus |
|---|---|---|
| Comeback King 👑 | Dropped below $25, recovered to $75+ | +10 MMR |
| Active Trader 💪 | Finished 20–50%, was actively trading | +3 MMR |

---

## Penalties

| Penalty | Trigger | Amount |
|---|---|---|
| Low Balance | Ended match with less than $25 | −10 MMR |
| Inactivity (15 min) | No trades in first 15 minutes | −10 MMR |
| Inactivity (30 min) | No trades in first 30 minutes | −20 MMR |
| Inactivity (45 min) | No trades in first 45 minutes | −30 MMR |
| AFK (Full Match) | No trades the entire match | −40 MMR |

---

## Streak System

**Building streak points:**
- Top 10% finish: +1.0 point
- Top 25% finish: +0.5 points
- Top 40% finish: +0.25 points
- Top 50%: maintains streak
- Below 50%: streak breaks (or uses protection)

**Streak levels:**
| Points | Status |
|---|---|
| 0–1.9 | — |
| 2–4.9 🔥 | Warming Up |
| 5–9.9 🔥🔥 | Hot |
| 10–14.9 🔥🔥🔥 | On Fire |
| 15+ ⚡ | Legendary |

**Streak Protection:** At 3+ streak points, players earn one protection charge — absorbs one bad game instead of resetting the streak.

**Milestone bonuses:** Reaching 5, 10, 15, and 20 streak points grants +10, +25, +50, and +100 MMR respectively.

---

## Rank Tiers

| Rank | Percentile | Season Reward | Decay? |
|---|---|---|---|
| 💎 Diamond | Top 1% | Exclusive Items | Yes — 25 MMR/day after 5-day grace |
| ⭐ Platinum | Top 5% | Premium Items | Yes — 15 MMR/day after 7-day grace |
| 🥇 Gold | Top 15% | Gold Package | No |
| 🥈 Silver | Top 35% | Silver Package | No |
| 🥉 Bronze | Top 60% | Bronze Package | No |
| 📈 Trader | Everyone | Participation | No |

Only Diamond and Platinum decay — keeping the top leaderboard competitive while casual players retain rank through breaks.

---

## Player Protection Systems

**New player protection (first 50–100 matches):** Losses scaled down, effective MMR floor to prevent early discouragement.

**Comeback boost:** Players below 1,000 MMR receive boosted gains and reduced losses.

**High MMR diminishing returns:** Above 4,000 MMR, gains reduce and losses increase. Above 6,000 MMR, losses capped at 3% per match.

**Season resets:** Full reset every 120 days — prevents permanent stratification, ensures new players can reach top rankings on merit.

---

## System Configuration

- Starting MMR: 1,000
- Soft cap: 4,000 (diminishing returns)
- Hard cap: 15,000
- Season length: 120 days

---

## Technical Validation

- 500,000+ MMR calculations stress-tested
- 8 player personas simulated across full seasons
- Overall satisfaction: 8/10 · Stability: 8.3/10 · Low Frustration: 8.4/10
- 100% test pass rate across all validation suites

---

## Integration

REMMR runs inside **Rade Engine**. It receives verified match results from REMM at match completion and processes all rating calculations server-side. Ratings are cosmetic — they do not affect matchmaking or match availability.

→ **Website:** https://chartraiders.com/gamified-trading  
→ **FAQ:** https://chartraiders.com/faq  
→ **Creator:** c0tt0nc4ndyta — Founder of Chart Raiders, Inventor of DayTradeSport

---

*Chart Raiders is the world's first DayTradeSport platform. REMMR is the first objective skill rating for competitive day trading — ranking players on performance, not promises. Game of Skill. Players never hold securities.*
