
# World Economic Indicators API - Real-Time Economic Data with FinanceFlowAPI

The World Economic Indicators API from FinanceFlowAPI provides real-time and historical data on key economic indicators, such as consumer credit, PMI, and GDP, from countries worldwide. Perfect for analysts, economists, and investors, this API enables tracking of global financial trends for informed decision-making. Integrate reliable economic data into your applications or dashboards with ease.

Sign up to get started and explore the full API at [financeflowapi.com/api_documentation](https://financeflowapi.com/api_documentation).

## Base URL
`https://financeflowapi.com/api/v1/`

All World Economic Indicators API endpoints follow this base URL.

---

## Endpoint: World Economic Indicators

**Endpoint:** `/world-indicators`  
**Description:** Retrieves real-time and historical data for specific economic indicators from a chosen country, such as consumer credit or manufacturing PMI.

### Request Parameters

- `api_key` (string, required): Your unique API key. [Get yours](https://financeflowapi.com).
- `country` (string, required): The country name (e.g., `"germany"`).
- `indicator_name` (string, required): The specific economic indicator (e.g., `"Consumer Credit"`).

### Request Example

```
GET https://financeflowapi.com/api/v1/world-indicators?api_key=YOUR_API_KEY&country=germany&indicator_name=Consumer%20Credit
```

### Response Example

```json
{
    "success": true,
    "code": 200,
    "message": "OK",
    "meta": {
        "timestamp": 1741363821,
        "request_id": "67cb1a6d8f942"
    },
    "data": [
        {
            "country": "Germany",
            "indicator_name": "Consumer Credit",
            "last": "235944000000.0",
            "previous": "235183000000.0",
            "units": "EUR",
            "report_date": "2024-12"
        }
    ]
}
```

---

## Why Choose FinanceFlowAPI?

- **Global Coverage**: Access economic indicators from multiple countries, including Germany, the US, and more.  
- **Affordable Plans**: Start with our free plan (200 requests/month) or upgrade to Standard ($10.99/month) or Premium ($20.99/month) for more data.  
- **Seamless Integration**: Comprehensive documentation with code samples.  
- **Future-Proof**: Upcoming endpoints include historical candles, financial statements, and SEC data.  

---

## Get Started

- Sign up to get your API key.  
- Explore the World Economic Indicators API documentation or this repository for details.  
- Test the endpoint with our free plan or unlock full access with a paid plan.  

⭐ Star this repository to support FinanceFlowAPI and stay updated on new features! For questions, open an issue or contact [support@financeflowapi.com](mailto:support@financeflowapi.com).

**FinanceFlowAPI**: Empowering fintech with real-time and historical financial data.
