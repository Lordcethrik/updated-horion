# NY Open VWAP Strategy Indicator (TradingView / Pine Script v6)

`ny_open_vwap_strategy.pine` is a VWAP indicator anchored to the NY session. It looks for price to bounce off the NY VWAP after the opening range has formed.

## Logic
1. **NY VWAP** is anchored at 09:30 ET.
2. **Opening Range (OR)** covers the first **30 min** by default. You can set it to 15. The OR is shaded, and its high and low are drawn as lines for the rest of the session.
3. **Setup Window** starts when the OR ends and lasts 90 min by default. Signals can only fire inside it.
4. **SELL**: price has closed below the OR low. It was fully below VWAP for N bars, then pulls back and touches VWAP (within a tolerance) and closes back below it on a red candle.
   **BUY** is the mirror image.
5. Each signal draws a **stop box** (beyond the signal candle or VWAP, plus a buffer) and a **target box** (a Reward:Risk multiple). The boxes close when the stop, the target or the session end is hit.
6. **Confluence table**: for MES, MNQ and MYM it shows whether price is above or below the NY VWAP, the Overnight VWAP (18:00 to 09:30) and the previous day's NY VWAP. It also shows the OR status (Inside, or Outside ▲/▼) and a trend score (Strong Up … Strong Down).

## Usage
Open TradingView's Pine Editor, paste the file, click **Add to chart**, and use a 1–5m chart. Alerts: "NY VWAP Sell" / "NY VWAP Buy", or "Any alert() function call" for messages that include entry, stop and target.

The optional filters (chart trend alignment, all table tickers agreeing) are in the **Signal Rules** input group.
