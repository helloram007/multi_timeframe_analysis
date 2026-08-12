# PipRunner Trend Indicator (Pine Script v6)

An advanced TradingView Pine Script v6 indicator implementing the **PipRunner Trend Strategy**, with strict **15-minute timeframe fractal calculations & entries**, Higher Timeframe (H4) direction filtering, dynamic H1 key levels, clean visual signals, and real-time alerts.

---

## 📈 Strategy Overview

The **PipRunner Trend** strategy is built specifically for the **15-minute timeframe**. All trade signals, Williams Fractals, market structure calculations, and entry/exit points are calculated strictly on **15M candles**.

### 🟢 Long Setup Criteria (15M Timeframe)
1. **EMA Trend Alignment**: 15M Fast EMA (36) > 15M Slow EMA (100).
2. **Pullback Confirmation**: A 15M Lower High fractal chevron forms during retracement.
3. **HTF Filter**: 4-Hour trend alignment (H4 Fast EMA > H4 Slow EMA).
4. **Entry Price**: 1 Pip above the 15M Lower High fractal peak (**Blue Dot** by default).
5. **Stop Loss**: 1 Pip below the most recent 15M fractal low (**Red Dot** by default).
6. **Take Profit**: 1:1 Reward-to-Risk ratio (**Green Dot** by default).

### 🔴 Short Setup Criteria (15M Timeframe)
1. **EMA Trend Alignment**: 15M Fast EMA (36) < 15M Slow EMA (100).
2. **Pullback Confirmation**: A 15M Higher Low fractal chevron forms during retracement.
3. **HTF Filter**: 4-Hour trend alignment (H4 Fast EMA < H4 Slow EMA).
4. **Entry Price**: 1 Pip below the 15M Higher Low fractal trough (**Blue Dot** by default).
5. **Stop Loss**: 1 Pip above the most recent 15M fractal high (**Red Dot** by default).
6. **Take Profit**: 1:1 Reward-to-Risk ratio (**Green Dot** by default).

---

## 🛠️ Key Features

- **Clutter-Free Visuals**: Removed signal target lines completely so the chart remains clean and uncluttered.
- **Subtle Signal Dots**: Signal dots default to **Size 1 (Tiny)** to keep price action crisp and readable.
- **15M-Only Signal & Dot Visibility**: Entry dots are displayed **ONLY when viewing the 15-minute chart**, keeping 1H, 4H, and higher timeframes completely clean.
- **Configurable Colors**:
  - Entry Dot Color (default: `Blue`).
  - Stop Loss Dot Color (default: `Red`).
  - Take Profit Dot Color (default: `Green`).
- **Clean Williams Fractals**: Displayed as clean chevrons (`shape.triangleup` / `shape.triangledown`) with **no text labels**.

---

## 📥 Installation

1. Open **[TradingView](https://www.tradingview.com)** and open your chart on the **15-minute (15m)** timeframe.
2. Click on the **Pine Editor** tab at the bottom of the screen.
3. Open [`PipRunner_Trend_Indicator.pine`](./PipRunner_Trend_Indicator.pine) and copy the code.
4. Paste the code into the Pine Editor, click **Save**, and click **Add to Chart**.

---

## ⚙️ Configuration Options

| Setting Group | Option Name | Default | Description |
| :--- | :--- | :--- | :--- |
| **EMA Settings** | Fast EMA Length | `36` | Fast Exponential Moving Average length (15M) |
| **EMA Settings** | Slow EMA Length | `100` | Slow Exponential Moving Average length (15M) |
| **Williams Fractals** | Left / Right Bars | `2` | Number of 15M bars required on each side to confirm a fractal |
| **Multi-Timeframe** | HTF Direction Timeframe | `240` (H4) | Timeframe for higher-timeframe trend filter |
| **Multi-Timeframe** | Filter M15 Signals with H4 | `true` | Restrict 15M entries to match H4 HTF direction |
| **Multi-Timeframe** | Key Levels Timeframe | `60` (H1) | Timeframe used for key support & resistance levels |
| **Signal & Risk** | Pip Offset | `1.0` | Number of pips added/subtracted for Entry & SL |
| **Signal & Risk** | Reward to Risk Ratio | `1.0` | Target profit multiplier relative to SL risk |
| **Visuals** | Entry Dot Color | `Blue` | Customizable Entry Dot color |
| **Visuals** | Stop Loss Dot Color | `Red` | Customizable Stop Loss Dot color |
| **Visuals** | Take Profit Dot Color | `Green` | Customizable Take Profit Dot color |
| **Visuals** | Signal Dot Size | `Size 1 (Tiny)` | Choose between Size 1 (Tiny) and Size 2 (Small) |

---

## 📁 Repository Structure

```
indicators/piprunner/
├── PipRunner_Trend_Indicator.pine  # Main TradingView Pine Script v6 indicator file
├── AGENTS.md                       # Workspace maintenance rules
└── README.md                       # Project documentation
```

---

## 📜 License
This indicator is open for personal trading, backtesting, and customization.
