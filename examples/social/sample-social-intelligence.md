# BORIS — Social Intelligence Report
**Target:** Protocol — *name redacted*
**Scan date:** 2026-03-02
**Engine:** BORIS beta 1.3 — Social Scanner v2.0
**Platforms analyzed:** 23

---

## Scores

```
🟠 Social Risk  : 43/100  ELEVATED
🟠 Social Trust : 31/100  WEAK

Platform impact on trust:
  ▼ Telegram : -35.6 pts
  ▼ X        :  -8.8 pts
```

---

## Platform Verdict

```
📨 Telegram : ✅ HEALTHY (by count)
   22 channels · 110,162 total followers
   2 official · 20 discovered/ecosystem

𝕏  X/Twitter : ⚠️ WEAK
   1 account · 315,842 followers

Overall: 🟠 WEAK SOCIAL PRESENCE
```

> High follower count does not mean healthy community.
> BORIS measures engagement quality, not vanity metrics.

---

## Official Accounts

### Telegram — @xxxxxxxx\_network
```
Followers    : 8,100
Engagement   : ⚠️ WEAK
Last Post    : 14d ago
Avg Views    : 606
View Ratio   : 7.5%
Source       : official (linked in README/website)
```

### Telegram — @xxxxxxxx\_network\_official\_chat (Group)
```
Followers    : 59,474
Engagement   : ⚠️ WEAK
Last Post    : 2d ago
Avg Views    : 606
Avg Reactions: 0.5
View Ratio   : 1.0%
Source       : official (linked in README/website)
```

```
59,474 members. 606 avg views. 0.5 reactions per post.
1.0% view ratio on a group this size = hollow community.
Either heavily bot-inflated, or community has disengaged.
```

### X/Twitter — @XxxxxxxNetwork
```
Followers    : 315,842
Tweets       : 2,859
Avg Views    : 9,262
Avg Reactions: 1,336.5
View Ratio   : 2.9%
Bio          : "Transforming the Future with #AI | 
               Permissionless Launchpad for DAOs & Memecoins..."
Source       : official
```

```
315,842 followers. 2.9% view ratio.
Threshold for healthy account: >10%.
Gap: 7.1 points below baseline.
Follower count inflated or audience disengaged.

Bio note: "AI | DAOs & Memecoins" — 
pivot language, not product-specific messaging.
```

---

## Discovered Ecosystem Channels

```
@xxxxxxxx_networkAn         7,281 followers  💀 DEAD
@dexeyarchive               8,398 followers  ⚠️ WEAK  (view ratio 99.8% — anomalous)
@whoisdexey                 8,120 followers  🚩 SUSPECT (view ratio 110.2%)
@xxxxxxxx_network_main      1,497 followers  💀 DEAD
@XxxxxxxprotocolXXXXXXX     7,046 followers  💀 DEAD
@dexencecommunity           1,955 followers  💀 DEAD
@dexenxd                    5,767 followers  💀 DEAD
@DeXe_network_ru              442 followers  💀 DEAD
@dexer_io                     519 followers  💀 DEAD
... + 11 more (dead or tiny)
```

```
Notable anomaly:
@whoisdexey — view ratio 110.2%
Views exceed subscriber count.
Indicates external traffic injection or view manipulation.
Content: SUSPECT classification.

@dexeyarchive — view ratio 99.8%
Near-perfect ratio is statistically unlikely for organic channels.
Suggests bot view amplification.
```

---

## Scam Impersonators — 5 Detected

```
These are third-party scam channels.
Users searching for official channels are at risk.

⚠️  @xxxx_network_official_chats
    impersonates @xxxx_network_official_chat
    (added trailing 's')

⚠️  @xxxx_networkk
    impersonates @Xxxx_network
    (doubled final letter)

⚠️  @xxxx_network_officiaI
    impersonates @Xxxx_network
    (capital I replacing lowercase l — visually identical)

⚠️  @xxxx_network_officialchat
    impersonates @xxxx_network_official_chat
    (removed underscore before 'chat')

⚠️  @xxxx_network_official_chatt
    impersonates @xxxx_network_official_chat
    (added trailing 't')
```

```
Detection method: Levenshtein distance + visual similarity
                  + character substitution patterns (I/l, 0/O)

5 active impersonators for one project is above average.
Indicates the project name has enough recognition to be
worth impersonating — but also signals active scam targeting
of the community.
```

---

## Risk Signals

```
🔴 HIGH — telegram.fake_followers
   7,281 subscribers, channel is dead (no recent activity)
   Followers purchased or accumulated, not organically active

🔴 HIGH — telegram.fake_followers
   5,767 subscribers, channel is dead
   Same pattern — bought following with no retention

🟠 MEDIUM — telegram.artificial_engagement
   8,100 subscribers, weak engagement
   Official channel underperforming its own size

🟠 MEDIUM — telegram.artificial_engagement
   8,398 subscribers, weak engagement (discovered channel)

🟠 MEDIUM — x.artificial_engagement
   View ratio 2.9% vs 10% threshold for 315,842 followers
   315K followers not converting to views

🟠 MEDIUM — cross_platform.cross_platform_mismatch
   Follower disparity: 2,487x across platforms
   (315,842 X vs 8,100 official TG)
   Organic growth would show more consistent ratios

... and 22 more signals (LOW — discovered channel structure)
```

---

## Positive Signals

```
✓ Active Telegram channel (last post 2d ago)
✓ Active Telegram group (last post 0d ago)
✓ Content analysis: 47 posts, no scam/shill patterns detected
✓ Presence on 3 healthy platforms, 383,416 total followers
✓ No coordinated pump language in analyzed content
✓ Official accounts linked consistently in README and website
```

---

## Content Analysis

```
Posts analyzed: 47 (Telegram) + X timeline
Scam patterns:  NONE detected
Shill patterns: NONE detected
Pump language:  NONE detected

Content is clean. Risk comes from engagement quality,
not content manipulation.
```

---

## Summary

```
Platforms analyzed  : 23
Official accounts   : 3
Total followers     : 383,416

Risk signals        : 39 total
  Critical          : 0
  High              : 2
  Medium            : 5
  Positive          : 6

Top concerns:
  1. Official Telegram group: 59K members, 1.0% view ratio
  2. X: 315K followers, 2.9% view ratio (below 10% threshold)
  3. 5 active impersonator channels
  4. Multiple dead channels with inflated follower counts
  5. Cross-platform follower disparity: 2,487x
```

---

## What This Means

```
This is not a "dead project with no community" pattern.
This is a "once-active community that has disengaged" pattern.

Indicators:
  + Content is clean (no active manipulation)
  + Official channels still posting
  + Large historical follower base

  - Engagement has collapsed relative to follower count
  - Multiple dead satellite channels suggest past growth push
  - Impersonators active = project has name recognition
    but insufficient community vigilance

Risk classification: WEAK PRESENCE
Not scam. Not dead. Just hollow.
```

---

*BORIS beta 1.3 — Social Scanner v2.0*
*Platforms: Telegram · X/Twitter · Discord*
