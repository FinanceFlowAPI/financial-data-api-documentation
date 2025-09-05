# Stock Tickers API - Real-Time Financial Data API for 511,000+ Tickers with FinanceFlowAPI

The **Stock Tickers API** from [FinanceFlowAPI](https://financeflowapi.com) is your ultimate **financial data API** for accessing real-time and metadata for over **511,000+ stock tickers**, including popular names like **AAPL** (Apple), **TSLA** (Tesla), **GOOGL** (Google), **MSFT** (Microsoft), and **AMZN** (Amazon). Perfect for traders, developers, and financial analysts, this API delivers unparalleled stock market data to power trading platforms, portfolio trackers, and market analysis tools. With FinanceFlowAPI, you get the most comprehensive **real-time stock data** in one place.

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
            "market": "us_market",
            "first_trade_date": "2004-08-02 13:30:00",
            "timezone": "America/New_York"
        },
        ...
    ]
}
```

### 2. Real-Time Stock Ticker Data
- **Endpoint**: `/ticker-spot`
- **Description**: Fetches real-time price and performance data for a specific stock ticker, such as **MSFT**, **AMZN**, or **GOOGL**, including current price, daily change, and historical performance metrics.

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
        "price": "203.890000",
        "change": "4.149994",
        "changePercent": "2.077698",
        "dayHigh": "208.000000",
        "dayLow": "202.799000",
        "volume": 29540691,
        "prevClose": "199.740000",
        "marketState": "REGULAR",
        "lastUpdated": "2025-04-23T16:51:33"
    }
}
```

## Why Choose FinanceFlowAPI?
- **Unmatched Scale**: Access **511,000+ stock tickers**, covering global markets and popular stocks like **AAPL**, **TSLA**, **GOOGL**, **MSFT**, and **AMZN**, outpacing competitors.
- **Affordable Plans**: Start with our [Test plan](https://financeflowapi.com/create-account/) (200 requests/month, only 5$) or upgrade to Standard ($25/month) or Premium ($50/month) for extensive **real-time stock data**.
- **Seamless Integration**: Comprehensive [documentation](https://financeflowapi.com/api_documentation/) with code samples for this **financial data API**.
- **Future-Proof**: Upcoming endpoints include historical candles, financial statements, and SEC data for deeper market insights.

## Get Started
1. [Sign up](https://financeflowapi.com/create-account/) to get your API key and dive into the **stock tickers API**.
2. Explore the [FinanceFlowAPI documentation](https://financeflowapi.com/api_documentation/) or this repository for details.
3. Test endpoints like `/ticker-spot` for **AAPL** or **TSLA** with our Test plan, or unlock full access with a paid plan.

Star this repository to support FinanceFlowAPI and stay updated on new features! For questions, open an [issue](https://github.com/FinanceFlowAPI/api-documentation/issues) or contact [support@financeflowapi.com](mailto:support@financeflowapi.com).

---
*FinanceFlowAPI: Empowering fintech with the ultimate financial data API for real-time and historical stock market data.*