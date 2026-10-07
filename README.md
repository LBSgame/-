# Stock Sim Trader · Beta 0.01

> A classroom virtual-stock-trading web app — real-time A-share quotes, virtual money, zero setup.

![version](https://img.shields.io/badge/version-Beta%200.01-orange)
![tech](https://img.shields.io/badge/tech-vanilla%20JS%20%2B%20ECharts-blue)
![data](https://img.shields.io/badge/data-Tencent%20Finance%20API-green)

## What is this?

A single-page stock simulator that runs straight in your browser. The quotes are **real-time A-share market data** (pulled from Tencent Finance), but the money is **virtual**. It is built so classmates can experience the full "buy → ride the ups and downs → sell" loop without spending a cent of real cash — perfect for a classroom investing game or a personal paper-trading sandbox.

## Features (Beta 0.01)

- **10 real stocks across 5 industries**
  - Gaming: 三七互娱 (SZ002555), 完美世界 (SZ002624)
  - Beauty: 珀莱雅 (SH603605), 贝泰妮 (SZ300957)
  - Stationery / Books: 晨光股份 (SH603899), 中信出版 (SZ300788)
  - AI tech: 科大讯飞 (SZ002230), 寒武纪 (SH688256)
  - Finance: 招商银行 (SH600036), 东方财富 (SZ300059)
- **Separate virtual account per classmate** — capital amounts can differ; a dark account bar shows the current student's cash, position value, and total assets, with a dropdown to switch players
- **Buy auto-deducts cash** — enter an amount, hit *Buy*, cash is deducted instantly, cost price weighted-averaged automatically
- **Sell anytime** — holdings table lists shares, cost, current price, P&L %; hit *Sell* (pick quantity or sell all) to cash out at the live price; realized P&L tracked separately
- **Live quotes** — auto-refresh every ~60s, red = up, green = down (A-share convention)
- **P&L bar chart** — unrealized profit per holding for the current student, rendered with ECharts
- **Manual save / reset** — progress persists in `localStorage`; hit *Save* to keep it, *Reset* to start a fresh round

## Quick start

1. Download `股票模拟交易.html` from the [Releases page](https://github.com/your-name/your-repo/releases).
2. Double-click the file — it opens in any modern browser (Chrome / Edge / Safari / mobile browser).
3. Add a few classmates (each with their own virtual capital), switch to one of them, and start buying/selling.

No server, no build step, no login required.

## How to play

1. Open the page → add classmates, give each a different starting capital (e.g. ¥1000).
2. Switch to a student in the top account bar.
3. In the quote cards, type an amount and click **Buy** — cash is deducted automatically.
4. Watch the holdings table; click **Sell** to take profit or cut losses.
5. After market close, compare total assets across classmates.

## Project structure

```
.
├── 股票模拟交易.html        # main app — buy / sell / per-student accounts / bar chart
├── 十股实时行情看板.html     # optional: a read-only live quote board
└── README.md
```

## Tech notes

- **Single self-contained HTML** — all CSS/JS inline, no framework, no build tooling.
- **Quotes**: Tencent Finance JSONP endpoint `https://qt.gtimg.cn/q=...`. Works from `file://` pages, no CORS setup needed.
- **Chart**: ECharts 5 (jsDelivr CDN, with cdnjs fallback).
- **Persistence**: `localStorage` — everything stays on the same browser/device.
- **Markets**: A-shares only; quotes update during China trading hours. Off-hours you'll see the previous close.

## Disclaimer

Market data is real; money is purely virtual. This project is for classroom simulation and learning purposes only — it is **not investment advice**.

## License

For educational use. Free to copy, modify and share with your class.
