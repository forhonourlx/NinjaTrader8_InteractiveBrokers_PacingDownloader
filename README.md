# NinjaTrader8_InteractiveBrokers_PacingDownloader
A python script for NinjaTrader8("NT8") users to obtain InteractiveBrokers("IB") historical data continuously(no interruption) without hitting pacing violations.

## Tested Software Version
- NinjaTrader 8.0.2.0 (December 5, 2016 released)
- IB Gateway 961a (IB API 9.72+)
- Python 3.5

## IB Pacing Violations
http://interactivebrokers.github.io/tws-api/historical_limitations.html

According to InteractiveBrokers Historical Data Limitations - Pacing Violations(if hitting the violations, a 5-min penalty disconnect will occur), the main obstacles from continously downloading are the following violations:
- Making six or more historical data requests for the same Contract, Exchange and Tick Type within two seconds.
- Making more than 60 requests within any ten minute period.
- Bars which size is 30 seconds or less older than six months.
- Note: BID_ASK counts as two requests.
- Note: The TWS is designed to accept up to 50 messages(i.e. requesting data, placing orders, requesting your portfolio... etc.) per second coming from the client side.
- Note: Old IB API guidelines state that each request should contain no more than 2000 bars.

|| *Bar Size* || *Valid Duration* ||

|| 1 Min || 2D, 1D, 4H, 2H, 1H... ||

|| 1 Tick(Sec) || 30Mins, 15Mins, 5Mins, 1Min... ||

## NinjaTrader8 Download Module
According to 'NinjaTrader8 - Historical Data - Load' module, users could choose the following items to download historical data:
- Intervals: Tick / Minute / Day
- Tick Types: Ask / Bid / Last
- Start Date & End Date
Unfortunately, NinjaTrader8 does not set a coldown for a too long requesting period and sometimes hit the IB violations .

## Continuous Download Solution
NinjaTrader8 is a "free"(as if no live trading) trading software, which has a nice database manager & downloader(able to export database) and well-tested connection with IB Gateway.
This script mainly imports *pywinauto* to implement a automation of NinjaTrader8 UI to realize IB historical data continuous download.
- For "Tick" data, requesting period would split into 30 Mins.
- For "Minute" data, requesting period would split into 2 Days.

## How to use
