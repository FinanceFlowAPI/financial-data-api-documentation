# Stock Tickers API - Real-Time Financial Data API for 511,000+ Tickers with FinanceFlowAPI

The **Stock Tickers API** from [FinanceFlowAPI](https://financeflowapi.com) provides real-time prices and metadata for over **511,000+ stock tickers**, including popular names like **AAPL** (Apple), **TSLA** (Tesla), **GOOGL** (Google), **MSFT** (Microsoft), and **AMZN** (Amazon). Built for traders, developers, and financial analysts, this API delivers comprehensive stock market data to power trading platforms, portfolio trackers, and market analysis tools.

[Sign up](https://financeflowapi.com/create-account/) to get started and explore the full **stock tickers API** at [financeflowapi.com/api_documentation](https://financeflowapi.com/api_documentation).

## Base URL
```
https://financeflowapi.com/api/v1/
```
All Stock Tickers API endpoints follow this base URL.

## Endpoints

### 1. Tickers Catalog
- **Endpoint**: `/tickers-catalog`
- **Description**: Retrieves a comprehensive catalog of over **511,000+ stock tickers**, including metadata like company names, exchanges, and industries for stocks like **AAPL**, **TSLA**, and **GOOGL**.

#### Request Parameters
- `api_key` (string, required): Your unique API key. [Get yours](https://financeflowapi.com/create-account/).
- `page` (integer, optional): Page number for pagination (default: 1).
- `ticker` (string, optional): Filter by specific ticker (e.g., "AAPL").
- `exchange` (string, optional): Filter by exchange (e.g., "NASDAQ").

#### Request Example
```
GET https://financeflowapi.com/api/v1/tickers-catalog?api_key=YOUR_API_KEY&page=1&exchange=ASE
```

#### Response Example
```json
{
    "success": true,
    "code": 200,
    "message": "OK",
    "meta": {
        "page": 1,
        "total_pages": 2,
        "total_items": 425,
        "tickers_per_page": 300,
        "timestamp": 1745423861,
        "request_id": "68090df504b96"
    },
    "data": [
        {
            "ticker": "TOPS",
            "company_name": "Top Ships Inc.",
            "exchange": "ASE",
            "full_exchange_name": "NYSE American",
            "currency": "USD",
            "first_trade_date": "2004-08-02 13:30:00",
            "timezone": "America/New_York"
        },
        ...
    ]
}
```

### 2. Real-Time Stock Ticker Data
- **Endpoint**: `/ticker-spot`
- **Description**: Fetches real-time price and performance data for a specific stock ticker, such as **MSFT**, **AMZN**, or **GOOGL**, including current price, daily change, day range, and market state. For historical OHLC data, use `/ticker-candles`.

#### Request Parameters
- `api_key` (string, required): Your unique API key.
- `ticker` (string, required): The stock ticker symbol (e.g., "AAPL").

#### Request Example
```
GET https://financeflowapi.com/api/v1/ticker-spot?api_key=YOUR_API_KEY&ticker=AAPL
```

#### Response Example
```json
{
    "success": true,
    "code": 200,
    "message": "OK",
    "meta": {
        "timestamp": 1745427151,
        "request_id": "68091acfb967b"
    },
    "data": {
        "ticker": "AAPL",
        "price": "313.185000",
        "change": "3.285004",
        "changePercent": "1.060021",
        "dayHigh": "313.450000",
        "dayLow": "308.800100",
        "volume": 7897450,
        "open": "310.245000",
        "prevClose": "309.900000",
        "marketState": "open",
        "lastUpdated": "2026-08-26T15:12:23"
    }
}
```

## Why Choose FinanceFlowAPI?
- **511,000+ Ticker Database**: Covering global markets and popular stocks like **AAPL**, **TSLA**, **GOOGL**, **MSFT**, and **AMZN**.
- **Affordable Plans**: Start with our [Test plan](https://financeflowapi.com/create-account/) ($5/month, 200 requests) or upgrade to Standard ($25/month) or Premium ($50/month) for extensive **real-time stock data**.
- **Clear Documentation**: [Documentation](https://financeflowapi.com/api_documentation/) with code samples for this **financial data API**.
- **More Than Spot Prices**: Pair this endpoint with the [Stock Ticker Candles API](ticker-candles-api.md) for historical OHLC data, or the [Income Statement](income-statement-api.md), [Balance Sheet](balance-sheet-api.md), and [Cash Flow](cash-flow-api.md) APIs for fundamentals.
- **Future-Proof**: Upcoming endpoints include SEC data (insider transactions).

## Get Started
1. [Sign up](https://financeflowapi.com/create-account/) to get your API key and dive into the **stock tickers API**.
2. Explore the [FinanceFlowAPI documentation](https://financeflowapi.com/api_documentation/) or this repository for details.
3. Test endpoints like `/ticker-spot` for **AAPL** or **TSLA** with our Test plan, or unlock full access with a paid plan.

Star this repository to support FinanceFlowAPI and stay updated on new features! For questions, open an [issue](https://github.com/FinanceFlowAPI/api-documentation/issues) or contact [support@financeflowapi.com](mailto:support@financeflowapi.com).

---
*FinanceFlowAPI: Empowering fintech with real-time and historical stock market data.*