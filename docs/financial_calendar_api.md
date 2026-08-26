# 📅 Financial Calendar API: Key Economic Events | FinanceFlowAPI

The **Financial Calendar API** from FinanceFlowAPI provides a detailed schedule of key economic events, market reports, and financial indicators across multiple countries.  
Essential for investors, traders, and analysts, this API helps you stay informed about upcoming events like PMI releases, interest rate decisions, and GDP reports that impact financial markets.

Integrate this data into your trading platforms or analytical tools to anticipate market movements.

👉 [Sign up](https://financeflowapi.com/api_documentation) to get started and explore the full API.

---

## 🔗 Base URL

```
https://financeflowapi.com/api/v1/
```

All Financial Calendar API endpoints follow this base URL.

---

## 📌 Endpoints

### 1. Supported Countries List

**Endpoint:** `/calendar-catalog`  
**Description:** Retrieves the list of 83 supported countries with available financial calendar data, such as Afghanistan, Albania, and the United States.

#### Request Parameters

| Parameter | Type   | Required | Description              |
|-----------|--------|----------|--------------------------|
| api_key   | string | Yes      | Your unique API key.     |

#### Request Example

```
GET https://financeflowapi.com/api/v1/calendar-catalog?api_key=YOUR_API_KEY
```

#### Response Example

```json
{
    "success": true,
    "code": 200,
    "message": "OK",
    "meta": {
        "timestamp": 1740778132,
        "request_id": "67c22a948bc91"
    },
    "data": [
        { "country": "Afghanistan" },
        { "country": "Albania" },
        ...
    ]
}
```

---

### 2. Financial Calendar

**Endpoint:** `/financial-calendar`  
**Description:** Retrieves a list of upcoming economic events for all available countries or a specific country.  
📅 **Note:** The period between `date_from` and `date_to` must not exceed 60 days.

#### Request Parameters

| Parameter   | Type   | Required | Description                              |
|-------------|--------|----------|------------------------------------------|
| api_key     | string | Yes      | Your unique API key.                     |
| country     | string | Yes      | Full country name (e.g., "United States") |
| date_from   | string | No       | Start date in YYYY-MM-DD format. Must be sent together with `date_to`. |
| date_to     | string | No       | End date in YYYY-MM-DD format. Must be sent together with `date_from`. |

💡 Tip: Use the exact country name as returned by `/calendar-catalog`.

#### Request Example

```
GET https://financeflowapi.com/api/v1/financial-calendar?api_key=YOUR_API_KEY&country=United States&date_from=2025-03-01&date_to=2025-03-07
```

#### Response Example

```json
{
    "success": true,
    "code": 200,
    "message": "OK",
    "meta": {
        "timestamp": 1740778240,
        "request_id": "67c22b003df2b"
    },
    "data": [
        {
            "country": "United States",
            "report_name": "Chicago Fed National Activity Index",
            "actual": "-0.08",
            "previous": "0.06",
            "consensus": "",
            "unit": "",
            "economicImpact": "Moderate",
            "report_date": "07",
            "datetime": "2026-08-24 12:30:00"
        },
        {
            "country": "United States",
            "report_name": "3-Month Treasury Bill Auction",
            "actual": "3.715",
            "previous": "3.715",
            "consensus": "",
            "unit": "percent",
            "economicImpact": "Standard",
            "report_date": "",
            "datetime": "2026-08-24 15:30:00"
        }
    ]
}
```

`actual` is an empty string for events that have not been released yet.

**`economicImpact` values explained:**  
- `"Standard"`: Minor expected influence  
- `"Moderate"`: Moderate market sensitivity  
- `"Major"`: Likely to cause notable market movements  

---

## ✅ Why Choose FinanceFlowAPI?

- 🌍 **Global Event Coverage:** Access economic event data from countries worldwide.  
- 💸 **Affordable Plans:** Start with our Test plan ($5/month, 200 requests) or upgrade to Standard ($25/month) or Premium ($50/month).  
- 🔌 **Clear Documentation:** Request/response examples and code samples for every endpoint.  
- 🔮 **Future-Proof:** Upcoming endpoints include SEC data.

---

## 🚀 Get Started

1. [Sign up](https://financeflowapi.com/api_documentation) to get your API key.
2. Explore the Financial Calendar API documentation or this repository for details.
3. Test the endpoints with our Test plan or unlock full access with a paid plan.

---

⭐ Star this repository to support FinanceFlowAPI and stay updated on new features!  
📩 For questions, open an issue or contact [support@financeflowapi.com](mailto:support@financeflowapi.com).

---

**FinanceFlowAPI: Empowering fintech with real-time and historical financial data.**