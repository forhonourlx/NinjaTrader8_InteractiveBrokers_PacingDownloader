# NinjaTrader8_InteractiveBrokers_PacingDownloader
A downloader script for NinjaTrader8 users to obtain InteractiveBrokers historical data continiously without hitting pacing violations.
## Pacing Violations
http://interactivebrokers.github.io/tws-api/historical_limitations.html

According to InteractiveBrokers Historical Data Limitations - Pacing Violations, the main obstacles from continously downloading are the following violations:
- Making six or more historical data requests for the same Contract, Exchange and Tick Type within two seconds.
- Making more than 60 requests within any ten minute period.
- Bars which size is 30 seconds or less older than six months.
