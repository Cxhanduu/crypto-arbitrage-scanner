# Crypto Arbitrage Scanner

A cryptocurrency arbitrage scanner that identifies price differences across multiple exchanges for profitable trading opportunities.

## Overview

This scanner monitors cryptocurrency prices across different exchanges in real-time and detects arbitrage opportunities where you can buy at one exchange and sell at another for a profit.

## Features

- **Multi-Exchange Support**: Monitor prices on Binance, Kraken, Coinbase, and more
- **Real-Time Price Monitoring**: Continuously scan for price discrepancies
- **Arbitrage Detection**: Automatically identify profitable trading opportunities
- **Fee Calculation**: Account for trading fees when calculating profits
- **Alert System**: Get notified when opportunities are found
- **Data Logging**: Track historical arbitrage opportunities
- **Dashboard**: View current opportunities and statistics

## Architecture

```
crypto-arbitrage-scanner/
├── config/                 # Configuration files
├── exchanges/              # Exchange API integrations
├── scanner/                # Core arbitrage scanning logic
├── utils/                  # Utility functions
├── alerts/                 # Alert system
├── data/                   # Data storage and logging
├── tests/                  # Unit tests
└── main.py                 # Entry point
```

## Requirements

- Python 3.8+
- pip or conda

## Installation

1. Clone the repository:
```bash
git clone https://github.com/Cxhanduu/crypto-arbitrage-scanner.git
cd crypto-arbitrage-scanner
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Configure API keys:
```bash
cp config/config.example.yaml config/config.yaml
# Edit config.yaml with your exchange API keys
```

## Quick Start

```bash
python main.py
```

## Configuration

Edit `config/config.yaml` to:
- Add exchange API credentials
- Set minimum profit threshold
- Configure alert channels
- Set scanning interval

## Usage

### Basic Scanning
```python
from scanner.arbitrage_scanner import ArbitrageScanner

scanner = ArbitrageScanner()
scanner.start()
```

### Custom Trading Pairs
```python
scanner = ArbitrageScanner(pairs=['BTC/USDT', 'ETH/USDT'])
scanner.start()
```

## Supported Exchanges

- Binance
- Kraken
- Coinbase
- Huobi
- KuCoin
- OKEx

## How Arbitrage Works

1. **Price Monitoring**: Fetch prices from multiple exchanges
2. **Comparison**: Identify price differences after accounting for fees
3. **Opportunity Detection**: Find buy/sell pairs with profit potential
4. **Execution**: Execute trades or alert user

Example:
```
Exchange A: BTC = $40,000
Exchange B: BTC = $41,000
Fee (each side): 0.1%

Profit = $41,000 - $40,000 - ($40,000 × 0.1%) - ($41,000 × 0.1%)
       = $1,000 - $40 - $41 = $919 (profit per BTC)
```

## Risk & Disclaimer

**⚠️ Important**: Arbitrage trading involves risks including:
- Price volatility during execution
- Network delays and execution risks
- Exchange API errors
- Regulatory compliance

This tool is for educational purposes. Use at your own risk and ensure compliance with local regulations.

## Performance Tips

- Adjust scanning frequency based on network capacity
- Filter by minimum profit to reduce noise
- Monitor API rate limits
- Use dedicated API keys with appropriate permissions

## Contributing

Contributions welcome! Please:
1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Open a Pull Request

## License

MIT License - See LICENSE file for details

## Support

For issues and questions, please open an issue on GitHub.
