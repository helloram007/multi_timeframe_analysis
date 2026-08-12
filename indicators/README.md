# Multi Timeframe (MTF) Analysis & Setup Engine (Pine Script v6)

An advanced TradingView Pine Script v6 indicator engineered to eliminate false counter-trend signals by combining **Dual HTF Trend Alignment (4H + 1H)** with **Lower Timeframe Momentum & Price Action Confluence**.

---

## 🛡️ Multi-Layer Confluence Engine

To prevent false signals and falling knives during deep corrections, entry signals require all 4 layers to align:

1. **Macro Higher Timeframe (4H / Daily)**:
   - **ADX > 25**: Confirms a strong trend environment.
   - **DMI (+DI vs -DI)**: Sets the directional trend bias (Bullish vs Bearish).
   - **Macro EMA Filter**: Price must be above the 200 EMA on the 4H timeframe.

2. **Intermediate Timeframe Alignment (1H)**:
   - Requires the **1H chart** to also align in direction (`1H Price > 1H 50 EMA` and `1H +DI > -DI`).
   - *Filters out*: Counter-trend entries when 1H is in a strong downward pullback.

3. **LTF Stochastic Oversold/Overbought Pullback**:
   - Longs require Stochastic %K to cross above %D while in **Oversold territory (<= 20)**.
   - Shorts require Stochastic %K to cross below %D while in **Overbought territory (>= 80)**.

4. **LTF Momentum & Price Action Confirmation**:
   - **LTF 20 EMA Filter**: Requires price to close above the LTF 20 EMA for Longs.
   - **LTF RSI Filter**: Requires RSI to be >= 45 (and rising) for Longs.
   - **Reversal Candle Filter**: Requires a green reversal candle (`Close > Open` and `Close > High[1]`) on the signal bar to confirm buyers have taken control.

---

## 📋 Installation Instructions

1. Open **TradingView** and load your target chart (e.g., EURUSD, BTCUSD).
2. Click **Pine Editor** at the bottom of the screen.
3. Select all text and replace it with the code from [`multi_timeframe_analysis.pine`](file:///c:/Users/rrapo/Documents/antigravity/multi_timeframe_analysis/multi_timeframe_analysis.pine).
4. Click **Save** and **Add to chart**.

---

## ⚙️ Filter Toggles & Customization

Inside indicator settings (`Gear icon -> Inputs`), you can individually toggle or adjust each filter:

- `1. Macro Higher Timeframe`: Set your Macro TF (`240` = 4H, `D` = Daily), ADX threshold (`25`), and Macro EMA (`200`).
- `2. Intermediate Timeframe`: Toggle `Require Intermediate HTF Alignment` on/off and set ITF (`60` = 1H).
- `3. Execution & LTF Confluence Filters`:
  - `Require Price > LTF EMA for Longs` (default: `20 EMA`)
  - `Require LTF RSI Momentum Confirmation` (default: `45` min for Longs)
  - `Require Reversal Candle Pattern` (requires green reversal candle on trigger bar)
