
# World Economic Indicators API - Real-Time Economic Data with FinanceFlowAPI

The World Economic Indicators API from FinanceFlowAPI provides real-time data on **663 economic indicators across 131 countries**, including consumer credit, PMI, and GDP. Built for analysts, economists, and investors, this API supports tracking global financial trends for informed decision-making. Integrate economic data into your applications or dashboards with a single endpoint.

Sign up to get started and explore the full API at [financeflowapi.com/api_documentation](https://financeflowapi.com/api_documentation).

## Base URL
`https://financeflowapi.com/api/v1/`

All World Economic Indicators API endpoints follow this base URL.

---

## Endpoint: World Economic Indicators

**Endpoint:** `/world-indicators`  
**Description:** Retrieves real-time data for a specific economic indicator from a chosen country, such as consumer credit or manufacturing PMI. The response returns the current (`last`) and prior (`previous`) report only; there is no historical time series for this endpoint.

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
            "last": "236859000000.0",
            "previous": "237345000000.0",
            "units": "EUR",
            "report_date": "2026-03"
        }
    ]
}
```

---

## Why Choose FinanceFlowAPI?

- **Global Coverage**: 663 economic indicators across 131 countries, including Germany, the US, and more.  
- **Affordable Plans**: Start with our Test plan ($5/month, 200 requests) or upgrade to Standard ($25/month) or Premium ($50/month) for more data.  
- **Clear Documentation**: Request/response examples and code samples for the endpoint.  
- **Future-Proof**: Upcoming endpoints include SEC data.  

---

## Get Started

- Sign up to get your API key.  
- Explore the World Economic Indicators API documentation or this repository for details.  
- Test the endpoint with our Test plan or unlock full access with a paid plan.  

⭐ Star this repository to support FinanceFlowAPI and stay updated on new features! For questions, open an issue or contact [support@financeflowapi.com](mailto:support@financeflowapi.com).

**FinanceFlowAPI**: Empowering fintech with real-time and historical financial data.
