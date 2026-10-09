# Global FX Bias Analyzer (Android starter)

Educational, demo-only Android prototype for forex majors and XAU/USD.

## What's included
- Kotlin + Jetpack Compose dashboard.
- Pair selector: EUR/USD, GBP/USD, USD/JPY, AUD/USD, USD/CAD, NZD/USD, XAU/USD.
- Demonstration bias score, BUY / SELL / NEUTRAL label.
- Illustrative entry, stop-loss and take-profit levels based on demo prices and ATR-like range.
- Fundamental/news/technical/risk score breakdown.
- API integration notes and safe configuration guidance.

## Important
This starter uses **simulated demo data**. It does not fetch live prices/news and does not place trades. Signals are educational examples, not financial advice or recommendations. Do not use the displayed prices or levels for real trading.

## Open in Android Studio
1. Install Android Studio with Android SDK.
2. Open this folder as a project.
3. Let Gradle sync.
4. Run on an Android emulator or Android device.

The Gradle wrapper is not bundled in this starter. Android Studio can create/use a compatible wrapper if needed.

## Connecting live data later
Use a backend service you control, not API keys embedded in the APK:
- Market prices/candles: a licensed market-data provider.
- Economic calendar: a provider with a permitted API and suitable coverage.
- News: licensed news API/RSS sources whose terms allow your use.
- Backend: fetches data, normalizes timestamps/symbols, caches results, and serves your app over HTTPS.

Keep API secrets on the backend, respect provider rate limits/redistribution rights, show each feed's last-updated timestamp, and fall back to "data unavailable" instead of inventing prices.

## Suggested scoring model (initial, unvalidated)
- Fundamental/rates & economic surprises: 35%
- News sentiment: 25%
- Technical trend/momentum: 30%
- Volatility/risk filter: 10%

A score is a heuristic, not a probability of profit. Validate it with out-of-sample historical testing before considering any real-world use.
