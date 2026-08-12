# Multi Timeframe (MTF) Analysis & Setup Engine (Pine Script v6)

An advanced TradingView Pine Script v6 indicator engineered to eliminate false counter-trend signals by combining **Dual HTF Trend Alignment (4H + 1H)** with **Lower Timeframe Momentum & Price Action Confluence**.

---

## 📈 Visual Trend Moving Averages (All Timeframes)

The indicator automatically plots key visual trend EMAs directly on your chart, adapting seamlessly across all timeframes (4H, 1H, 15M, 5M, etc.):

- **20 EMA (Light Blue)**: Fast short-term momentum trend line.
- **50 EMA (Red)**: Intermediate trend support/resistance line.
- **200 EMA (Green)**: Macro trend direction line.

---

## 📊 4-Column Real-Time Dashboard Matrix

| Timeframe | Matrix Item | Status / Value | Setup |
| :--- | :--- | :--- | :--- |
| **4H** | Macro ADX (25+) | `34.2 (Strong)` | `PASS` |
| **4H** | Macro Bias | `+DI > -DI (Above EMA)` | `BULLISH` |
| **1H** | Intermed Trend | `Close > 50 EMA` | `BULLISH` |
| **15m** | Stoch (%K / %D) | `%K: 18.4 \| %D: 15.2` | `BULL CROSS` |
| **15m** | Fast EMA (20) | `Close > 20 EMA (1.0924)` | `BULL PASS` |
| **15m** | RSI (14) | `RSI: 52.4` | `PASS (>= 45)` |
| **15m** | Reversal Candle | `Green (C > H[1])` | `BULL PASS` |
| **All TF**| Overall Confluence | `All 7 Filters Passed` | `🟢 LONG READY` |

---

## 🛡️ Multi-Layer Confluence Engine

1. **Macro Higher Timeframe (4H / Daily)**:
   - **ADX > 25**: Confirms a strong trend environment.
   - **DMI (+DI vs -DI)**: Sets the directional trend bias (Bullish vs Bearish).
   - **Macro EMA Filter**: Price must be above the 200 EMA on the 4H timeframe.

2. **Intermediate Timeframe Alignment (1H)**:
   - Requires the **1H chart** to also align in direction (`1H Price > 1H 50 EMA` and `1H +DI > -DI`).

3. **LTF Stochastic Oversold/Overbought Pullback**:
   - Longs require Stochastic %K to cross above %D while in **Oversold territory (<= 20)**.
   - Shorts require Stochastic %K to cross below %D while in **Overbought territory (>= 80)**.

4. **LTF RSI & Momentum Confirmation**:
   - **LTF RSI Filter**: Displays live RSI numeric value (e.g. `RSI: 52.4`) and requires `RSI >= 45` for Longs.
   - **LTF 20 EMA Filter**: Requires price to close above the LTF 20 EMA for Longs.
   - **Reversal Candle Filter**: Requires a green reversal candle (`Close > Open` and `Close > High[1]`).

---

## 📋 Installation Instructions

1. Open **TradingView** and load your target chart.
2. Click **Pine Editor** at the bottom of the screen.
3. Select all text and replace it with the code from [`multi_timeframe_analysis.pine`](file:///c:/Users/rrapo/Documents/antigravity/multi_timeframe_analysis/indicators/multi_timeframe_analysis.pine).
4. Click **Save** and **Add to chart**.
