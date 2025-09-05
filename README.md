# FinanceFlowAPI Documentation

Welcome to the official documentation for **FinanceFlowAPI**, a powerful financial API providing real-time and historical data for:

- **Commodities** (gold, coal, oil, agricultural products)
- **Government Bonds** (e.g., US, Germany, Australia)
- **Stock Indices** (DE40, ASX200, S&P 500, etc.)
- **Stock Tickers** (real-time prices for **511,000+ tickers** like AAPL, TSLA, GOOGL)
- **Economic Indicators** (PMI, consumer credit, etc.)
- **Financial Calendar** (key economic events)

Whether you're building trading platforms, market analysis tools, or financial dashboards, **FinanceFlowAPI** offers reliable and affordable data to empower your fintech projects.

> 🔑 **Sign up today** at [financeflowapi.com/create-account](https://financeflowapi.com/create-account) and start exploring our API!

---

## 🚀 Why FinanceFlowAPI?

- **Comprehensive Data**: Real-time and historical datasets for commodities, bonds, stocks, and more.
- **Affordable Pricing**: Test plan with 200 requests/month, only 5$. Paid plans start at **$25/month**.
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
           "current_price": 2797.16,
           "daily_change": "10.50",
           "daily_change_percent": "0.38%",
           "last_updated": "2025-01-31"
       }
   }
   ```

---

## 🗂️ Documentation Structure

This repository includes detailed documentation for each endpoint in the `/docs` folder:

- Commodity API: Real-time and historical data for commodities (e.g., gold, coal).

**Planned**:

- Bonds API: Real-time and historical government bond yields (`/bonds-spot`, `/bonds-history`).
- Stock Tickers API: Real-time prices and catalog for 511,000+ tickers (`/ticker-spot`, `/tickers-catalog`).
- Economic Indicators: Consumer credit, PMI, and more (`/world-indicators`).
- Financial Calendar: Key economic events (`/financial-calendar`).

See the official documentation for the full list.

---

## 💰 Pricing Plans

|   Plan    |   Price   | Requests/Month | Historical Data |
|    ---    |    ---    |      ---       |      ---        | 
| Test      | $5/month  | 200            | 365 days        |
| Standard  | $25/month | 10,000         | 180 days        |
| Premium   | $50/month | 100,000        | Unlimited       | 

📌 See the pricing page for details.

---

## 🔮 What's Next?

We’re actively working on:

- 📊 **Historical Candles**: OHLC data for stock tickers.
- 📈 **Financial Statements**: Balance sheet, income statement, cash flow.
- 🧾 **SEC Data**: Insider transactions and filings.

⭐ **Star this repository** to follow updates!

---

## 💬 Support

- **Questions or suggestions?** Open a GitHub issue.
- **Email**: support@financeflowapi.com.
- **Docs**: financeflowapi.com/api_documentation.

---

## 🤝 Contribute

We’re a growing API and value your feedback! Share your use case, suggest new endpoints, or report issues via GitHub Issues. Let us know if you’re using FinanceFlowAPI — we’d love to feature your project!

---

**FinanceFlowAPI — Empowering fintech with real-time and historical financial data.**