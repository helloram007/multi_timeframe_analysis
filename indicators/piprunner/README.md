# PipRunner Trend Indicator (Pine Script v6)

An advanced TradingView Pine Script v6 indicator implementing the official **SmartCharts PipRunner Trend Strategy**, with strict **15-minute breakout entry triggers**, Higher Timeframe (H4) direction filtering, dynamic H1 key levels, chop-prevention filters, and real-time alerts.

---

## 📈 Strategy Overview & SmartCharts Signal Rules

The **PipRunner Trend** strategy evaluates market structure, 36 & 100 EMAs, and Williams Fractal chevrons strictly on the **15-minute timeframe**:

### 🟢 Long Setup Rules (SmartCharts Official)
1. **EMA Trend Alignment**: 15M Fast EMA (36) > 15M Slow EMA (100).
2. **Lower High Fractal Chevron (`^`)**: Price pulls back during an uptrend and forms a **Lower High Up Fractal (`^`)**.
3. **HTF Filter**: 4-Hour trend alignment (H4 Fast EMA > H4 Slow EMA).
4. **Buy Entry Level**: **1 Pip ABOVE the most recent fractal high** (**Blue Diamond**).
5. **Stop Loss Level**: **1 Pip BELOW the most recent fractal low** (**Red Dot**).
6. **Take Profit Level**: **1:1 Reward to Risk** relative to Entry and Stop Loss (**Green Dot**).

### 🔴 Short Setup Rules (SmartCharts Official)
1. **EMA Trend Alignment**: 15M Fast EMA (36) < 15M Slow EMA (100).
2. **Higher Low Fractal Chevron (`v`)**: Price pulls back during a downtrend and forms a **Higher Low Down Fractal (`v`)**.
3. **HTF Filter**: 4-Hour trend alignment (H4 Fast EMA < H4 Slow EMA).
4. **Sell Entry Level**: **1 Pip BELOW the most recent fractal low** (**Blue Diamond**).
5. **Stop Loss Level**: **1 Pip ABOVE the most recent fractal high** (**Red Dot**).
6. **Take Profit Level**: **1:1 Reward to Risk** relative to Entry and Stop Loss (**Green Dot**).

---

## 🛠️ Key Features

- **SmartCharts Breakout Engine**: Solved signal clutter by requiring price to actively break out above/below the fractal trigger level before firing a signal.
- **Official 1:1 R:R Calculation**: Computes exact Entry, Stop Loss (1 pip offset), and Take Profit (1:1 R:R).
- **Visual Fractal Chevrons**: Displays clean Green Up-Triangles (`^`) above bars and Red Down-Triangles (`v`) below bars matching SmartCharts graphics.
- **ADX & EMA Chop Filters**: Suppresses setups during non-trending sideways markets when ADX(14) < 20 or EMAs squeeze.
- **15M-Only Signal Visibility**: Entry signals display **ONLY when viewing the 15-minute chart**, keeping 1H and 4H charts completely clean.

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
| **EMA Settings** | Fast / Slow EMA Length | `36` / `100` | Fast and Slow EMA lengths |
| **Williams Fractals** | Left / Right Bars | `2` | Number of 15M bars required on each side for fractal |
| **False Signal Filters** | Filter Chop with ADX | `true` | Suppress setups when ADX < 20 |
| **Multi-Timeframe** | HTF Direction Timeframe | `240` (H4) | Timeframe for higher-timeframe trend filter |
| **Multi-Timeframe** | Key Levels Timeframe | `60` (H1) | Timeframe for dynamic support & resistance levels |
| **Signal & Risk** | Take Profit Target Mode | `Fixed R:R Multiplier` | Select Fixed R:R vs Dynamic H1 Key Level TP |
| **Signal & Risk** | Reward to Risk Ratio | `1.0` | Target profit multiplier (SmartCharts default: 1:1) |

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
