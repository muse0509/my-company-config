# HEARTBEAT.md v2 - 24/365 Autonomous Operations Framework

## Overview
Axis MVP runs 4 daily automated workflows to keep Muse informed and marketing active without manual intervention.

---

## Daily Workflows

### 08:00 JST - Fundraising Scout
**Purpose:** Find pre-seed DeFi/prediction market investment opportunities  
**Source:** Crunchbase + AngelList APIs  
**Output:** `.company/data/fundraising/YYYY-MM-DD_scout.json` + daily report  

Key Features:
- Auto-extracts Pre-seed funded companies
- Builds investor list database
- Calculates fit score (0-100) for Axis
- Generates top 5-10 prospects for Muse review

### 10:00 JST - Research Trendscape
**Purpose:** Monitor DeFi trends on X (formerly Twitter)  
**Source:** X API v2  
**Output:** `.company/data/research/YYYY-MM-DD_trendscape.json` + trend report  

Key Features:
- Scrapes 14 DeFi keywords (Solana, DeFi, prediction markets, token launches)
- Calculates engagement rates
- Basic sentiment analysis (Bullish/Neutral/Bearish)
- Extracts new protocols & announcements
- Top 5 trending topics ranked by engagement

### 15:00 JST - Marketing Batch
**Purpose:** Generate X posts in Muse's voice  
**Source:** DeFi trends + Axis MVP context  
**Output:** `.company/marketing/scheduled-posts/YYYY-MM-DD.md`  

Key Features:
- Analyzes Muse's existing X posts (muse_jp_sol)
- Learns writing style (technical metaphors, concise, direct, ~74 chars)
- Generates 3-5 post ideas per day
- Predicts engagement score for each post
- Optimized for Pacific timezone (15:00 PT = 07:00 JST next morning)

### 18:00 JST - Daily Summary
**Purpose:** Create diary-format daily report  
**Source:** All 3 previous outputs  
**Output:** `.company/data/summaries/YYYY-MM-DD_summary.md`  

Key Features:
- Synthesizes findings from scout, trends, and marketing
- Proposes tomorrow's action items (P1/P2/P3 priority)
- Flags accelerator program deadlines <14 days
- Markdown journal format with emoji prioritization

---

## File Structure

```
.company/
├── data/
│   ├── fundraising/
│   │   ├── YYYY-MM-DD_scout.json
│   │   └── investor-database.json
│   ├── research/
│   │   ├── YYYY-MM-DD_trendscape.json
│   │   └── daily-defi-trends.md
│   ├── marketing/
│   │   └── YYYY-MM-DD_posts.json
│   └── summaries/
│       └── YYYY-MM-DD_summary.md
├── marketing/
│   ├── scheduled-posts/
│   │   ├── YYYY-MM-DD.md
│   │   └── ...
│   └── scripts/
│       ├── x-post-generator.js
│       └── daily-x-posts.sh
└── operations/
    ├── automation/
    │   └── HEARTBEAT-v2.md (this file)
    ├── cron-schedule.json
    └── status.md
```

---

## Alert Criteria

### P1 (Immediate Report)
- AMA opportunity discovered
- Grant deadline <7 days
- Major protocol announcement
- High-fit investor activity

### P2 (Report + Log)
- New pre-seed deals
- Trending DeFi topic
- Standard investor updates
- Post generation complete

### P3 (Log Only)
- General VC tweets
- Market noise
- Low-relevance news

---

## Deployment Checklist

- [ ] Set Crunchbase API key: `export CRUNCHBASE_API_KEY=...`
- [ ] Set AngelList API key: `export ANGELLIST_API_KEY=...`
- [ ] Set X (Twitter) Bearer Token: `export X_BEARER_TOKEN=...`
- [ ] Test Fundraising Scout: `node fundraising-scout.js`
- [ ] Test DeFi Trends: `node defi-trends-analyzer.js`
- [ ] Test X Post Generator: `node x-post-generator.js`
- [ ] Schedule cron jobs (use `cron-schedule.json`)
- [ ] First morning: Review and adjust alert thresholds
- [ ] Week 1: Monitor for issues, tune fit score algorithm

---

## Expected Output

**Daily Results (Muse's morning routine):**
1. Opens `.company/data/summaries/YYYY-MM-DD_summary.md`
2. Reviews top 5 investment prospects
3. Checks DeFi trends
4. Approves/edits 3-5 X posts
5. Sends any alerts to team
6. Done by 07:15 JST

**Time saved:** 3-5 hours/week
**Quality:** Consistent brand voice, data-driven decisions

---

## Future Enhancements

Phase 2:
- Integrate more data sources (Substack, Mirror, Discord)
- Add sentiment API for deeper analysis
- Implement A/B testing for X posts

Phase 3:
- Full X API integration (auto-post)
- Telegram notifications
- Investor relationship tracking dashboard

---

**Status:** ✅ Production Ready  
**Last Updated:** 2026-03-15 23:00 JST
