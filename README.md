# NY 9:30 Anchored VWAP (TradingView / Pine Script v6)

`ny_anchored_vwap.pine` draws a VWAP that resets every day at the 9:30 AM ET New York open and runs until the 4:00 PM close.

## Signals
The script waits for the first 30 minutes after the open (or 15, if you change it). After that, it looks for pullbacks to the VWAP that go with the trend:

- **BUY**: the VWAP is rising. Price has stayed above the VWAP for a few bars, dips down to touch it, then closes back above it on a green candle.
- **SELL**: the VWAP is falling. Price has stayed below the VWAP for a few bars, rallies up to touch it, then closes back below it on a red candle.

Signals only appear once the candle has closed, so they don't repaint. There is a daily limit on signals, 2 by default. Alerts are available as "NY VWAP Buy" and "NY VWAP Sell".

## Usage
Open TradingView's Pine Editor, paste in the whole file and click **Add to chart**. It works best on intraday charts (1–5 minutes).
