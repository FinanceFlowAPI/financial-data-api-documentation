# Stock Index Spot API - Real-Time Stock Index Data with FinanceFlowAPI

The **Stock Index Spot API** from [FinanceFlowAPI](https://financeflowapi.com) provides real-time data on global stock indices, such as DE40, ASX200, and S&P 500, including price changes, regional classification, and performance trends. Essential for investors, analysts, and financial institutions, this API enables monitoring of market trends for informed investment decisions. Integrate seamless index data into your trading platforms or analytical tools.

[Sign up](https://financeflowapi.com/create-account/) to get started and explore the full API at [financeflowapi.com/api_documentation](https://financeflowapi.com/api_documentation).

## Base URL
```
https://financeflowapi.com/api/v1/
```
All Stock Index Spot API endpoints follow this base URL.

## Endpoints

### 1. Supported Benchmark List
- **Endpoint**: `/index-catalog`
- **Description**: Retrieves a list of all available stock indices (benchmarks), such as ADX General, ASE, ASPI, and ASX200.

#### Request Parameters
- `api_key` (string, required): Your unique API key. [Get yours](https://financeflowapi.com/create-account/).

#### Request Example
```
GET https://financeflowapi.com/api/v1/index-catalog?api_key=YOUR_API_KEY
```

#### Response Example
```json
{
    "success": true,
    "code": 200,
    "message": "OK",
    "meta": {
        "timestamp": 1743339544,
        "request_id": "67e9401854175"
    },
    "data": [
        {"benchmark": "adx general"},
        {"benchmark": "ase"},
        {"benchmark": "aspi"},
        {"benchmark": "ASX200"}
    ]
}
```

### 2. Stock Index Spot Data
- **Endpoint**: `/index-spot`
- **Description**: Retrieves real-time stock index data for a specified country or benchmark, including current price, daily change, and performance metrics.

#### Request Parameters
- `api_key` (string, required): Your unique API key.
- `country` (string, optional): The country for which to retrieve index data (e.g., "germany").
- `benchmark` (string, optional): The specific benchmark to retrieve (e.g., "de40"). Use either `country` or `benchmark`.

#### Request Examples
**By Country**:
```
GET https://financeflowapi.com/api/v1/index-spot?api_key=YOUR_API_KEY&country=germany
```
**By Benchmark**:
```
GET https://financeflowapi.com/api/v1/index-spot?api_key=YOUR_API_KEY&benchmark=de40
```

#### Response Example
```json
{
    "success": true,
    "code": 200,
    "message": "OK",
    "meta": {
        "timestamp": 1743340626,
        "request_id": "67e94452c1b30"
    },
    "data": {
        "benchmark": "de40",
        "country": "germany",
        "region": "europe",
        "price": 22462,
        "daily_change": "217",
        "daily_change_percent": "-0.96%",
        "monthly_change_percent": "-2.96%",
        "yearly_change_percent": "22.85%",
        "last_updated": "2025-03-28"
    }
}
```

## Why Choose FinanceFlowAPI?
- **Global Index Coverage**: Access data on stock indices from Europe, Asia, the Americas, and beyond.
- **Affordable Plans**: Start with our [Test plan](https://financeflowapi.com/create-account/) (200 requests/month, only 5$) or upgrade to Standard ($25/month) or Premium ($50/month) for more data.
- **Seamless Integration**: Comprehensive [documentation](https://financeflowapi.com/api_documentation/) with code samples.
- **Future-Proof**: Upcoming endpoints include historical candles, financial statements, and SEC data.

## Get Started
1. [Sign up](https://financeflowapi.com/create-account/) to get your API key.
2. Explore the [Stock Index Spot API documentation](https://financeflowapi.com/api_documentation/) or this repository for details.
3. Test the endpoints with our Test plan or unlock full access with a paid plan.

Star this repository to support FinanceFlowAPI and stay updated on new features! For questions, open an [issue](https://github.com/FinanceFlowAPI/api-documentation/issues) or contact [support@financeflowapi.com](mailto:support@financeflowapi.com).

---
*FinanceFlowAPI: Empowering fintech with real-time and historical financial data.*