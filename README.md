# NinjaTrader8_InteractiveBrokers_PacingDownloader
A python script for NinjaTrader8 users to obtain InteractiveBrokers("IB") historical data continiously without hitting pacing violations.

## Tested Software Version
- NinjaTrader8 
- IB Gateway 961a (IB API 9.72+)
- Python 3.5

## IB Pacing Violations
http://interactivebrokers.github.io/tws-api/historical_limitations.html

According to InteractiveBrokers Historical Data Limitations - Pacing Violations, the main obstacles from continously downloading are the following violations:
- Making six or more historical data requests for the same Contract, Exchange and Tick Type within two seconds.
- Making more than 60 requests within any ten minute period.
- Bars which size is 30 seconds or less older than six months.

## NinjaTrader8 Download Module
According to 'NinjaTrader8 - Historical Data - Load' module, 
