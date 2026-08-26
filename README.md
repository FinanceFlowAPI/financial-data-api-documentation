# FinanceFlowAPI Documentation

Welcome to the official documentation for **FinanceFlowAPI**, a powerful financial API providing real-time and historical data for:

- **Commodities** (gold, coal, oil, agricultural products)
- **Government Bonds** (e.g., US, Germany, Australia)
- **Stock Indices** (DE40, ASX200, S&P 500, etc.)
- **Stock Tickers** (real-time prices for **511,000+ tickers** like AAPL, TSLA, GOOGL, plus historical candles and financial statements)
- **Economic Indicators** (PMI, consumer credit, etc.)
- **Financial Calendar** (key economic events)

Whether you're building trading platforms, market analysis tools, or financial dashboards, **FinanceFlowAPI** offers reliable and affordable data to empower your fintech projects.

> 🔑 **Sign up today** at [financeflowapi.com/create-account](https://financeflowapi.com/create-account) and start exploring our API!

---

## 🚀 Why FinanceFlowAPI?

- **Comprehensive Data**: Real-time and historical datasets for commodities, bonds, stocks, and more.
- **Affordable Pricing**: Test plan at $5/month (200 requests). Paid plans start at **$25/month**.
- **Easy Integration**: Well-documented with examples in Python, JavaScript, and more.
- **Future-Ready**: Upcoming endpoints include SEC data.

---

## 📘 Getting Started

1. **Sign Up**: Create an account to get your API key.

2. **Explore Docs**: Visit API Documentation or check the `/docs` folder in this repository.

3. **Test the API**: Try endpoints like `/commodity-spot` with the Test plan (limited access to some endpoints, e.g., no `/ticker-spot`).

4. **Integrate**: Use the example below:

   ```bash
   GET https://financeflowapi.com/api/v1/commodity-spot?api_key=YOUR_API_KEY&name=Gold
   ```

   **Response Example**:

   ```json
   {
       "success": true,
       "code": 200,
       "message": "OK",
       "meta": {
           "timestamp": 1740775729,
           "request_id": "67c221313880a"
       },
       "data": {
           "commodity_name": "gold",
           "current_price": 4599.06,
           "daily_change": "-59.05",
           "daily_change_percent": "-1.27%",
           "last_updated": "2026-08-26"
       }
   }
   ```

---

## 🗂️ Documentation Structure

This repository includes detailed documentation for each endpoint category in the `/docs` folder:

- [Commodity API](docs/commodity-api.md): Real-time and historical data for 102 commodities (e.g., gold, coal).
- [Government Bonds API](docs/government-bonds-api.md): Real-time and historical bond yields for 54 countries (`/bonds-spot`, `/bonds-history`).
- [Currency API](docs/currency-api.md): Real-time exchange rates for 628 currency pairs (`/currency-spot`, `/currency-catalog`).
- [Stock Index API](docs/index-api.md): Real-time data for 86 stock index benchmarks (`/index-spot`, `/index-catalog`).
- [Stock Tickers API](docs/tickers-api.md): Real-time prices and catalog for 511,000+ tickers (`/ticker-spot`, `/tickers-catalog`).
- [Stock Ticker Candles API](docs/ticker-candles-api.md): Historical daily OHLC candles for stock tickers (`/ticker-candles`).
- [World Economic Indicators API](docs/indicators-api.md): 663 economic indicators across 131 countries (`/world-indicators`).
- [Financial Calendar API](docs/financial_calendar_api.md): Key economic events for 83 countries (`/financial-calendar`).
- [Income Statement API](docs/income-statement-api.md): Quarterly and annual income statements (`/ticker-income-statement`).
- [Balance Sheet API](docs/balance-sheet-api.md): Quarterly and annual balance sheets (`/ticker-balance-sheet`).
- [Cash Flow API](docs/cash-flow-api.md): Quarterly and annual cash flow statements (`/ticker-cash-flow`).

See the [official documentation](https://financeflowapi.com/api_documentation/) for the full endpoint list.

---

## 💰 Pricing Plans

|   Plan    |   Price   | Requests/Month | Requests/Minute | Historical Data |
|    ---    |    ---    |      ---       |       ---        |      ---        |
| Test      | $5/month  | 200            | 20              | 60 days         |
| Standard  | $25/month | 10,000         | 60              | 5 years         |
| Premium   | $50/month | 100,000        | 120             | 20+ years       |

📌 See the [pricing page](https://financeflowapi.com/#pricing) for details; plans and limits may change over time.

---

## 🔮 What's Next?

- 🧾 **SEC Data**: Insider transactions and filings.

⭐ **Star this repository** to follow updates!

---

## 💬 Support

- **Questions or suggestions?** Open a GitHub issue.
- **Email**: support@financeflowapi.com.
- **Docs**: financeflowapi.com/api_documentation.

---

## 🤝 Contribute

We’re a growing API and value your feedback! Share your use case, suggest new endpoints, or report issues via GitHub Issues. Let us know if you’re using FinanceFlowAPI: we’d love to feature your project!

---

**FinanceFlowAPI: Empowering fintech with real-time and historical financial data.**