# Davinciecode.EA - Trading Expert Advisor

**Version:** v0.3.0-alpha  
**Language:** MQL5 (MetaTrader 5)  
**Strategy:** Institutional Breakout with Market Structure Detection

## Overview

Davinciecode.EA is a professional-grade Expert Advisor designed for institutional-style trading with emphasis on:
- **Market Structure Detection** - Identifying support/resistance and swing highs/lows
- **Institutional Breakout Engine** - Recognizing institutional price action patterns
- **Liquidity Sweep Detection** - Detecting liquidity hunter patterns
- **Retest Validation** - Confirming breakout legitimacy
- **Multi-Timeframe Analysis** - M1, M5, M15, H1 synchronized analysis

## Project Structure

```
Davinciecode.EA/
├── Expert/                 # Main Expert Advisor files
│   └── Davinciecode.EA.mq5
├── Indicators/             # Custom indicators
│   ├── MarketStructure.mq5
│   ├── BreakoutDetector.mq5
│   └── LiquiditySweep.mq5
├── Libraries/              # Reusable MQL5 libraries
│   ├── MarketStructure.mqh
│   ├── BreakoutEngine.mqh
│   ├── LiquidityDetector.mqh
│   ├── RetestValidator.mqh
│   ├── SignalFilter.mqh
│   └── ConfidenceScorer.mqh
├── Python/                 # Python integration & analysis
│   ├── data_analyzer.py
│   ├── api_connector.py
│   └── requirements.txt
├── Config/                 # Configuration & profiles
│   ├── strategy_profiles.json
│   └── trading_settings.ini
├── Docs/                   # Documentation
│   ├── README.md
│   ├── INSTALLATION.md
│   ├── STRATEGY_GUIDE.md
│   └── API_REFERENCE.md
└── Tests/                  # Unit tests & backtest results
    └── backtest_results.txt
```

## Version Roadmap

### v0.2.0-alpha ✓
- Core Infrastructure
- Trading Framework
- Orchestration

### v0.3.0-alpha (CURRENT)
- ✓ Market Structure Detection
- ✓ Institutional Breakout Engine
- ✓ Liquidity Sweep Detection
- ✓ Retest Validation
- ✓ Signal Filtering
- ✓ Confidence Scoring
- ✓ Strategy Profiles

### v0.4.0-alpha (PLANNED)
- Advanced Liquidity Analysis
- ML-based Pattern Recognition
- Real-time Risk Management
- Portfolio Optimization

## Key Features

### 🎯 Market Structure Detection
- Multi-timeframe swing analysis
- Support/Resistance identification
- Structure breaks and retests
- Higher Highs/Higher Lows (HHLL) patterns

### 💥 Institutional Breakout Engine
- Breakout confirmation logic
- False breakout filtering
- Institutional accumulation zones
- Smart entry positioning

### 💧 Liquidity Detection
- Liquidity sweep identification
- Stop loss hunt patterns
- Volume profile analysis
- Institutional order flow recognition

### ✅ Retest Validation
- Breakout retest confirmation
- Fair value gap (FVG) analysis
- Premium/Discount zone validation
- Entry optimization

### 📊 Multi-Timeframe Analysis
- Synchronized analysis: M1, M5, M15, H1
- Timeframe correlation
- Higher timeframe bias confirmation
- Trend alignment validation

## Installation

1. **MetaTrader 5 Setup:**
   - Copy Expert Advisor to: `C:\Users\[User]\AppData\Roaming\MetaQuotes\Terminal\[TerminalID]\MQL5\Experts\`
   - Copy Indicators to: `C:\Users\[User]\AppData\Roaming\MetaQuotes\Terminal\[TerminalID]\MQL5\Indicators\`
   - Copy Libraries to: `C:\Users\[User]\AppData\Roaming\MetaQuotes\Terminal\[TerminalID]\MQL5\Include\`

2. **Compile:**
   - Open MetaTrader 5
   - Navigate to File > Open Data Folder
   - Open MQL5\Experts folder
   - Right-click on Davinciecode.EA.mq5 > Compile

3. **Configuration:**
   - Edit strategy_profiles.json with your settings
   - Adjust trading_settings.ini parameters
   - Backtest on historical data

## Quick Start

```mql5
// In Expert Advisor:
#include "Libraries\MarketStructure.mqh"
#include "Libraries\BreakoutEngine.mqh"
#include "Libraries\ConfidenceScorer.mqh"

// Initialize
CMarketStructure structure;
CBreakoutEngine breakout;
CConfidenceScorer scorer;

// On each tick
structure.Analyze(Symbol(), PERIOD_M1, PERIOD_M5, PERIOD_M15, PERIOD_H1);
breakout.DetectBreakout(structure);
double confidence = scorer.CalculateSignalConfidence(breakout, structure);
```

## Configuration

### Strategy Profiles (strategy_profiles.json)
- **Aggressive:** High risk, fast entries, tight stops
- **Conservative:** Low risk, confirmation-heavy, wider stops
- **Scalper:** M1/M5 focus, quick profits
- **Swing:** H1/D1 focus, trend trading

### Trading Settings (trading_settings.ini)
```ini
[TIMEFRAMES]
TF1 = M1
TF2 = M5
TF3 = M15
TF4 = H1

[RISK_MANAGEMENT]
MaxRiskPerTrade = 2.0
PositionSize = 1.0
StopLossMultiplier = 1.5

[MARKET_STRUCTURE]
SwingHighPeriod = 5
SwingLowPeriod = 5
BreakoutBuffer = 10
```

## External API Support

- **MetaTrader 5 Native:** Direct tick data
- **REST APIs:** Binance, Forex brokers
- **Python Bridge:** Real-time data analysis

## Documentation

- **INSTALLATION.md** - Detailed setup guide
- **STRATEGY_GUIDE.md** - Trading strategy explanation
- **API_REFERENCE.md** - Library function reference

## Testing & Backtesting

All strategies are backtested across multiple market conditions:
- Trending markets
- Ranging markets
- High volatility periods
- Low liquidity conditions

See `Tests/backtest_results.txt` for performance metrics.

## Support & Development

- **Issues:** Report bugs via GitHub Issues
- **Discussions:** Strategy discussions in GitHub Discussions
- **Pull Requests:** Contributions welcome!

## License

MIT License - See LICENSE file

## Disclaimer

**⚠️ RISK WARNING:** Trading involves substantial risk of loss. This EA is provided for educational purposes. Past performance does not guarantee future results. Use proper risk management and never trade with capital you cannot afford to lose.

---

**Author:** Davinciecode1  
**Last Updated:** 2026-07-08  
**Status:** Alpha - Use for testing/backtesting only
