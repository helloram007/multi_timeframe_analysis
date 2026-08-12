# Multi Timeframe (MTF) Analysis & Setup Engine (Pine Script v6)

An advanced TradingView Pine Script v6 indicator engineered to catch high-win-rate trends early using **3-Bar Reversal Patterns on EMA Retests after CHoCH/BoS**, **SMC Liquidity Sweeps**, and **Dual HTF Trend Alignment (4H + 1H)**.

---

## ⚡ 3-Bar Reversal Pattern Entry Mechanics

When price performs a retest of the **20, 50, or 200 EMA support zone** after a CHoCH / BoS break, entries are confirmed using a **3-Bar Reversal Pattern**:

1. **Bar 1**: Downward bar dipping into EMA support.
2. **Bar 2**: Sweep bar making a lower low into EMA support (`low[1] < low[2]`), sweeping liquidity.
3. **Bar 3**: Strong bullish confirmation candle closing **above the high of Bar 2** (`Close > Open` & `Close > High[1]`).

---

## ⚙️ Signal Mode Options

- `3-Bar Reversal Retest (SMC)` *(New!)*
- `SMC CHoCH + Triple EMA Sweep`
- `Golden Cross + 200 EMA Retest`
- `Early Impulse (20x50 Cross)`
- `Post-Cross Retest`
- `Both (Impulse + Retest)` *(Default - includes 3-Bar Reversals & Retests)*

---

## 📋 Installation Instructions

1. Open **TradingView** and load your target chart.
2. Click **Pine Editor** at the bottom of the screen.
3. Select all text and replace it with the code from [`multi_timeframe_analysis.pine`](file:///c:/Users/rrapo/Documents/antigravity/multi_timeframe_analysis/indicators/multi_timeframe_analysis.pine).
4. Click **Save** and **Add to chart**.
