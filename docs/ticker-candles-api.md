# Stock Ticker Candles API - Historical OHLC Data with FinanceFlowAPI

The **Stock Ticker Candles API** from [FinanceFlowAPI](https://financeflowapi.com) provides daily OHLC (open, high, low, close) candles and volume for any of our **511,000+ stock tickers**. It complements the [Stock Tickers API](tickers-api.md)'s real-time `/ticker-spot` endpoint by adding the historical price series needed for charting, backtesting, and trend analysis.

[Sign up](https://financeflowapi.com/create-account/) to get started and explore the full API at [financeflowapi.com/api_documentation](https://financeflowapi.com/api_documentation).

## Base URL
```
https://financeflowapi.com/api/v1/
```

## Endpoint

### Historical Ticker Candles
- **Endpoint**: `/ticker-candles`
- **Description**: Retrieves daily OHLC candles for a specific stock ticker. Without `date_from`/`date_to`, returns the most recent candles available under your plan.

#### Request Parameters
- `api_key` (string, required): Your unique API key.
- `ticker` (string, required): The stock ticker symbol (e.g., "AAPL").
- `date_from` (string, optional): Start date in YYYY-MM-DD format. Must be provided together with `date_to`.
- `date_to` (string, optional): End date in YYYY-MM-DD format. Must be provided together with `date_from`.

**Notes:**
- The difference between `date_from` and `date_to` must not exceed 366 days.
- Future dates are not allowed.
- How far back you can query is governed by your plan's historical data allowance, see [Pricing Plans](../README.md#-pricing-plans).

#### Request Example
```
GET https://financeflowapi.com/api/v1/ticker-candles?api_key=YOUR_API_KEY&ticker=AAPL&date_from=2026-08-01&date_to=2026-08-05
```

#### Response Example
```json
{
    "success": true,
    "code": 200,
    "message": "OK",
    "meta": {
        "timestamp": 1787758537,
        "request_id": "6a8f07c9b0731"
    },
    "data": [
        {
            "ticker": "AAPL",
            "open": "309.359985",
            "high": "311.709991",
            "low": "305.670013",
            "close": "311.000000",
            "adj_close": "311.000000",
            "volume": 49438800,
            "date": "2026-08-05"
        },
        {
            "ticker": "AAPL",
            "open": "302.730011",
            "high": "310.420013",
            "low": "301.320007",
            "close": "309.380005",
            "adj_close": "309.380005",
            "volume": 68001000,
            "date": "2026-08-04"
        }
    ]
}
```

#### Errors
| Code | When | Message |
|------|------|---------|
| 400 | `ticker` missing | `required parameters not found, please specify one of: [ticker]` |
| 400 | only one of `date_from`/`date_to` provided | `Both date_from and date_to must be provided.` |
| 400 | invalid date format | `Invalid date format. Please use YYYY-MM-DD.` |
| 400 | date range exceeds 366 days | `Invalid date range. The difference between date_from and date_to must not exceed 366 days.` |
| 400 | `date_from`/`date_to` in the future | `Future dates are not allowed.` |
| 400 | date range exceeds your plan's historical data allowance | `Your plan allows access to historical data for the last N days only` |
| 404 | `ticker` not found | `Data not found, please check your request.` |

## Why Choose FinanceFlowAPI?
- **Deep Ticker Coverage**: Daily candles for any of our 511,000+ stock tickers.
- **Affordable Plans**: Start with our [Test plan](https://financeflowapi.com/create-account/) ($5/month, 200 requests) or upgrade to Standard ($25/month) or Premium ($50/month) for a longer historical window.
- **Clear Documentation**: Request/response examples and a full error reference for every endpoint.
- **Pairs with `/ticker-spot`**: Combine real-time quotes with historical candles using the same `api_key`.

## Get Started
1. [Sign up](https://financeflowapi.com/create-account/) to get your API key.
2. Explore the [Stock Tickers API documentation](https://financeflowapi.com/api_documentation/) or this repository for details.
3. Test the endpoint with our Test plan or unlock a longer historical window with a paid plan.

Star this repository to support FinanceFlowAPI and stay updated on new features! For questions, open an [issue](https://github.com/FinanceFlowAPI/api-documentation/issues) or contact [support@financeflowapi.com](mailto:support@financeflowapi.com).

---
*FinanceFlowAPI: Empowering fintech with real-time and historical financial data.*
