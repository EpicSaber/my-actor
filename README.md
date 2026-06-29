[My Actor](https://apify.com/scenic_bookmark/my-actor?fpr=data)

# Instagram Intelligence Engine 🚀

**Stop guessing. Measure Instagram performance.**

This is not just a scraper. It is an **Intelligence Engine** that turns raw public Instagram data into actionable insights.

- **Audits Influencers** ("Is this account healthy?")
- **Spots Trends** ("Is this hashtag rising?")
- **Prevents Blocking** (Enterprise-grade anti-detection)

## 🧠 Instant Intelligence Features

Unlike basic scrapers that dump raw JSON, this engine computes **Premium Insights**:

### 1. Influencer Audit Mode (Profile)

Answers: *"Is this creator worth collaborating with?"*

- **Engagement Rating**: Automatic grading (e.g., "VIRAL >5%", "HIGH >3%").
- **Account Health**: Detects dormant accounts or potential bots.
- **Growth Signal**: Identifies accounts with recent velocity spikes.
- **Lead Gen**: Extracts **Emails** & **Phones** from bios.

### 2. Viral Discovery Mode (Reels)

Answers: *"What content format is working right now?"*

- **Velocity Analysis**: Views per hour calculation.
- **Audio Trend Identification**.

### 3. Hashtag Research Mode

Answers: *"Is this niche dead or alive?"*

- **Top Post Analysis**.
- **Co-occurrence**: Find related tags.

## ⚡ Turbo Speed Mode (God Mode)

Toggle `fastMode: true` to enable high-velocity scraping.

- **Instant Scroll**: Bypasses human emulation for instant page traversal.
- **Zero-Wait Navigation**: Scrapes data as soon as the DOM is ready (`domcontentloaded`).
- **Micro-Latency**: Delays reduced to 100-300ms for machine-speed execution.
- **Resource Blocking**: Aggressively blocks images, fonts, and analytics.

> **Warning**: this mode is essentially "Bot Mode". Use with caution.

## 🛡️ Anti-Blocking Technology

Built on Apify SDK v3 + Crawlee + Playwright:

- **Session Pools**: Persisted cookies & headers.
- **Human Emulation**: Randomized scrolling & mouse movements.
- **Adaptive Retries**: Smart handling of login walls.

## Input Configuration

The Actor accepts the following input options:

```
{
    "mode": "profile", // "profile" | "hashtag" | "reels"
    "targets": ["apifytech", "instagram"], // usernames, hashtags, or URLs
    "maxItems": 50, // Max items to scrape per target
    "scrollLimit": 6, // Max scrolls per page
    "proxyType": "residential", // "residential" (recommended) or "datacenter"
    "delayMinMs": 2500,
    "delayMaxMs": 6000
}
```

## 💎 Premium Output Structure

We structure data so you see the **Answer** first.

```
{
    "summary": {
        "username": "apifytech",
        "account_health": "HEALTHY (Contactable)",
        "engagement_rating": "HIGH (>3%)",
        "growth_signal": "POSITIVE_SIGNAL",
        "contact_status": "HAS_EMAIL",
        "followers": 15200
    },
    "profile_details": {
        "full_name": "Apify",
        "public_email": "contact@apify.com",
        "biography": "Web scraping made easy...",
        "is_verified": true
    },
    "engagement_metrics": {
        "engagementRate": 3.45,
        "avgLikes": 450,
        "avgComments": 12
    },
    "latest_posts": [...]
}
```