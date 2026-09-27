# Base44 development notes

- This repository is a single static `index.html`; the browser directly calls CoinGecko's public API for 200-day BTC/XAUT price history. No local backend, database, or API credential is required to serve it.
- Use `docker compose -f docker-compose.base44.yml up -d --build` to run the Vite development server on port 3000. The source is bind-mounted, so edits to `index.html` update the preview without rebuilding.
- Verify with `curl http://localhost:3000/` and look for the page title; price loading additionally depends on CoinGecko's availability and rate limits from the viewer's browser.
