# ELISY254 Auto Trade

A static, mobile-friendly Deriv digit market scanner with separate **Market Scan Only** and opt-in **Auto Trade** modes.

## Deploy on Vercel

This repository is a static HTML app; it does not require a build command or server runtime.

1. Open https://vercel.com/new and import `bethanyhellen210-alt/Auto-trade`.
2. Set Framework Preset to **Other**.
3. Leave Build Command and Output Directory empty/default; the site entry point is `index.html`.
4. Deploy. New commits to the connected production branch will trigger deployments automatically.

CLI (from a clone of this repository):

```bash
npm i -g vercel
git clone https://github.com/bethanyhellen210-alt/Auto-trade.git
cd Auto-trade
vercel login
vercel --prod
```

## Use

- Connect to Deriv public tick data to use scanning without authorizing an account.
- Auto-trade requires a Deriv API token with appropriate trading permissions. Token input is kept in page memory only and is not written to browser localStorage.
- The initial auto-trade implementation is intentionally restricted to a maximum of 10 sequential contracts, fixed stakes, a maximum stake setting, a session loss limit, and a stop after 3 consecutive losses. Auto-trade is off by default.
- Test with a demo account first. Verify contract parameters, account currency, and live API behavior before risking real funds. Risk checks cannot eliminate losses, and digit patterns do not guarantee predictive advantage.

## Limitations

- Single-page browser app; no backend, user accounts, persistent trade journal, or server-side credential vault.
- Initial execution supports Over 4, Under 5, Even, and Odd digit contracts.
- Current auto-trade currency guard only permits USD accounts to avoid silently submitting an amount in a different currency.
- A browser disconnect or closing the tab stops future entries but cannot guarantee cancellation of a contract already purchased. Check Deriv directly for open contracts.
- Signals are heuristic filters, not financial advice or a proven profitable strategy.
