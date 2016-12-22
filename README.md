# NinjaTrader8_InteractiveBrokers_PacingDownloader
A python script for NinjaTrader8("NT8") users to obtain InteractiveBrokers("IB") historical data continiously without hitting pacing violations.

## Tested Software Version
- NinjaTrader 8.0.2.0 (December 5, 2016 released)
- IB Gateway 961a (IB API 9.72+)
- Python 3.5

## IB Pacing Violations
http://interactivebrokers.github.io/tws-api/historical_limitations.html

According to InteractiveBrokers Historical Data Limitations - Pacing Violations, the main obstacles from continously downloading are the following violations:
- Making six or more historical data requests for the same Contract, Exchange and Tick Type within two seconds.
- Making more than 60 requests within any ten minute period.
- Bars which size is 30 seconds or less older than six months.
- Note: BID_ASK counts as two requests.
- Note: The TWS is designed to accept up to 50 messages(i.e. requesting data, placing orders, requesting your portfolio... etc.) per second coming from the client side.

|| *Bar Size* || *Valid Duration* ||

|| 1 Min || 2D, 1D, 4H, 2H, 1H... ||

|| 1 Tick(Sec) || 30Mins, 15Mins, 5Mins, 1Min... ||

## NinjaTrader8 Download Module
According to 'NinjaTrader8 - Historical Data - Load' module, users could choose:
- Intervals: Tick / Minute / Day
- Start Date & End Date
- Tick Types: Ask / Bid / Last
to download historical data.

## Continuous Download Solution
NinjaTrader8 is a "free"(as if no live trading) trading software, which has a nice database manager & downloader and well-tested connection with IB Gateway.

