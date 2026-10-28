# ELISY254 Public Market Scanner

A mobile-friendly, static Deriv digit scanner. It reads public tick data and does not request a Deriv password or API token. This build does not authorize accounts or place trades.

## Deploy on Vercel

1. Import https://github.com/bethanyhellen210-alt/Auto-trade at https://vercel.com/new.
2. Choose **Other** as the Framework Preset.
3. Leave Build Command, Install Command, and Output Directory empty/default.
4. Deploy the project. The static entry point is `index.html`; no environment variables are required.

## Add the scanner to elisy.store

After deploying, copy the public Vercel deployment URL from your Vercel project. In the page editor for your website, add an HTML/embed block and paste this iframe. Replace `YOUR-VERCEL-DOMAIN` with the exact hostname Vercel assigned to this project (do not include a trailing slash).

```html
<div style="width:100%;max-width:1200px;margin:0 auto;">
  <iframe
    src="https://YOUR-VERCEL-DOMAIN/?embed=1"
    title="ELISY254 public Deriv market scanner"
    loading="lazy"
    style="display:block;width:100%;height:900px;border:0;border-radius:12px;"
    allow="clipboard-read; clipboard-write"
  ></iframe>
</div>
```

For a mobile page, you can reduce the iframe height to suit your website layout. The `?embed=1` option hides the scanner's standalone header and footer so it fits more neatly inside your page.

## Public data and account access

- The scanner connects to Deriv's public WebSocket tick feed using a public app ID.
- No API-token input, account authorization, account balance, or trade execution is included in this version.
- Public market data cannot authorize real trades. If you later want account linking, register a Deriv OAuth application with an exact HTTPS callback URL and implement the OAuth flow before enabling trading. Do not collect or paste users' passwords or API tokens into this page.

## Limitations

- Static frontend only; no backend, user accounts, or server-side credential storage.
- Signal rules are heuristic observations, not proven predictive advantage or financial advice.
- Live feed availability depends on Deriv's service and the visitor's network.
