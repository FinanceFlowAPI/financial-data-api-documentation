# Commodity API - Real-Time and Historical Commodity Data with FinanceFlowAPI

The **Commodity API** from [FinanceFlowAPI](https://financeflowapi.com) provides real-time and historical market data for **102 commodities**, including gold, oil, coal, agricultural products, and freight/commodity indices. Built for financial analysts, traders, and developers, this API delivers up-to-date commodity prices and trends to power trading platforms, market analysis tools, and financial dashboards.

[Sign up](https://financeflowapi.com/create-account/) to get started and explore the full API at [financeflowapi.com/api_documentation](https://financeflowapi.com/api_documentation).

## Base URL
```
https://financeflowapi.com/api/v1/
```
All Commodity API endpoints follow this base URL.

## Endpoints

### 1. Supported Commodities List
- **Endpoint**: `/commodity-catalog`
- **Description**: Retrieves the complete list of 102 supported commodities available in the API, such as aluminum, barley, coal, and gold.

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
        "last_updated": "2026-08-26"
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
GET https://financeflowapi.com/api/v1/commodity-history?api_key=YOUR_API_KEY&name=Gold&interval=day&date_from=2026-08-01&date_to=2026-08-05
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
            "date": "2026-08-05",
            "price": 4247.4
        },
        {
            "date": "2026-08-04",
            "price": 4077.86
        },
        ...
    ]
}
```

## Why Choose FinanceFlowAPI?
- **Broad Commodity Coverage**: 102 commodities across metals, energy, agriculture, and freight/commodity indices, alongside our stock, bond, and currency data.
- **Affordable Plans**: Start with our [Test plan](https://financeflowapi.com/create-account/) ($5/month, 200 requests) or upgrade to Standard ($25/month) or Premium ($50/month) for extensive data access.
- **Clear Documentation**: [Documentation](https://financeflowapi.com/api_documentation/) with request/response examples for every endpoint.
- **Future-Ready**: Upcoming endpoints include SEC data (insider transactions).

## Get Started
1. [Sign up](https://financeflowapi.com/create-account/) to get your API key.
2. Explore the [Commodity API documentation](https://financeflowapi.com/api_documentation/) or this repository for details.
3. Test the endpoints with our Test plan or unlock real-time data with a paid plan.

Star this repository to support FinanceFlowAPI and stay updated on new features! For questions, open an [issue](https://github.com/FinanceFlowAPI/api-documentation/issues) or contact [support@financeflowapi.com](mailto:support@financeflowapi.com).

---
*FinanceFlowAPI: Empowering fintech with real-time and historical commodity data.*