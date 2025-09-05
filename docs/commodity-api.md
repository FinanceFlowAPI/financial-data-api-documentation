# Commodity API - Real-Time and Historical Commodity Data with FinanceFlowAPI

The **Commodity API** from [FinanceFlowAPI](https://financeflowapi.com) provides real-time and historical market data for commodities like gold, oil, coal, and agricultural products. Perfect for financial analysts, traders, and developers, this API delivers up-to-date commodity prices and trends to power trading platforms, market analysis tools, and financial dashboards. With a massive database of **511,000+ tickers**, FinanceFlowAPI offers unparalleled coverage for your fintech needs.

[Sign up](https://financeflowapi.com/create-account/) to get started and explore the full API at [financeflowapi.com/api_documentation](https://financeflowapi.com/api_documentation).

## Base URL
```
https://financeflowapi.com/api/v1/
```
All Commodity API endpoints follow this base URL.

## Endpoints

### 1. Supported Commodities List
- **Endpoint**: `/commodity-catalog`
- **Description**: Retrieves a complete list of supported commodities available in the API, such as aluminum, barley, coal, and gold.

#### Request Parameters
- `api_key` (string, required): Your unique API key. [Get yours](https://financeflowapi.com/create-account/).

#### Request Example
```
GET https://financeflowapi.com/api/v1/commodity-catalog?api_key=YOUR_API_KEY
```

#### Response Example
```json
{
    "success": true,
    "code": 200,
    "message": "OK",
    "meta": {
        "timestamp": 1740778358,
        "request_id": "67c22b7644819"
    },
    "data": [
        {
            "name": "aluminum"
        },
        {
            "name": "barley"
        },
        ...
    ]
}
```

### 2. Real-Time Commodity Price
- **Endpoint**: `/commodity-spot`
- **Description**: Fetches the latest price of a specific commodity in real-time, including current price, daily change, and performance metrics.

#### Request Parameters
- `api_key` (string, required): Your unique API key.
- `name` (string, required): The name of the commodity (e.g., "Coal", "Gold").

#### Request Example
```
GET https://financeflowapi.com/api/v1/commodity-spot?api_key=YOUR_API_KEY&name=Coal
```

#### Response Example
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
        "commodity_name": "coal",
        "current_price": 100.1,
        "daily_change": "2.30",
        "daily_change_percent": "-2.25%",
        "weekly_change_percent": "-3.29%",
        "monthly_change_percent": "-12.99%",
        "ytd_change_percent": "-20.08%",
        "yearly_change_percent": "-23.59%",
        "last_updated": "2024-09-20"
    }
}
```

### 3. Historical Commodity Data
- **Endpoint**: `/commodity-history`
- **Description**: Retrieves historical price data for a specific commodity over a given period, ideal for trend analysis and backtesting. The period between `date_from` and `date_to` must not exceed 100 days.

#### Request Parameters
- `api_key` (string, required): Your unique API key.
- `name` (string, required): The name of the commodity (e.g., "Gold").
- `interval` (string, required): The data interval (`day` or `month`).
- `date_from` (string, optional): Start date in YYYY-MM-DD format.
- `date_to` (string, optional): End date in YYYY-MM-DD format.

#### Request Example
```
GET https://financeflowapi.com/api/v1/commodity-history?api_key=YOUR_API_KEY&name=Gold&interval=day&date_from=2025-01-01&date_to=2025-01-31
```

#### Response Example
```json
{
    "success": true,
    "code": 200,
    "message": "OK",
    "meta": {
        "timestamp": 1740776956,
        "request_id": "67c225fc0cf7a"
    },
    "data": [
        {
            "date": "2025-01-31",
            "price": 2797.16
        },
        {
            "date": "2025-01-30",
            "price": 2796.18
        },
        ...
    ]
}
```

## Why Choose FinanceFlowAPI?
- **Unmatched Coverage**: Access **511,000+ tickers**, including commodities, stocks, bonds, and more, surpassing competitors like Finnhub or FMP.
- **Affordable Plans**: Start with our [Test plan](https://financeflowapi.com/create-account/) (200 requests/month, only 5$) or upgrade to Standard ($25/month) or Premium ($50/month) for extensive data access.
- **Seamless Integration**: Comprehensive [documentation](https://financeflowapi.com/api_documentation/) with clear examples.
- **Future-Ready**: Upcoming endpoints include SEC data (insider transactions).

## Get Started
1. [Sign up](https://financeflowapi.com/create-account/) to get your API key.
2. Explore the [Commodity API documentation](https://financeflowapi.com/api_documentation/) or this repository for details.
3. Test the endpoints with our Test plan or unlock real-time data with a paid plan.

Star this repository to support FinanceFlowAPI and stay updated on new features! For questions, open an [issue](https://github.com/FinanceFlowAPI/api-documentation/issues) or contact [support@financeflowapi.com](mailto:support@financeflowapi.com).

---
*FinanceFlowAPI: Empowering fintech with 511,000+ tickers and real-time data.*