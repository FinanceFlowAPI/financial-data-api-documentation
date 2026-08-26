
# 🇺🇸 Government Bonds API: Real-Time & Historical Bond Yields

The **Government Bonds API** from [FinanceFlowAPI](https://financeflowapi.com) provides real-time and historical bond yield data for major economies including the **United States**, **Germany**, **Australia**, and more.

📈 Ideal for:
- Investors & traders
- Financial analysts
- Research platforms
- Fintech & macroeconomic tools

Integrate accurate bond yield data into your dashboards or apps with **just a few lines of code**.

---

## 🌐 Base URL

```
https://financeflowapi.com/api/v1/
```

---

## 📘 API Endpoints

### 1. ✅ Supported Countries List

Retrieve a list of the 54 countries with available bond data, plus the maturities (types) supported for each.

**Endpoint:**  
`GET /bonds-catalog`

**Request Parameters:**
- `api_key` (string, required): Your API key.

**Example:**
```
GET /bonds-catalog?api_key=YOUR_API_KEY
```

**Response:**
```json
{
  "success": true,
  "code": 200,
  "message": "OK",
  "data": [
    { "country": "Austria", "supported_types": ["10y"] },
    { "country": "Australia", "supported_types": ["10y", "20y", "2y", "30y", "3y", "52w", "5y", "7y"] }
  ]
}
```

---

### 2. 📊 Real-Time Government Bond Yields

Fetch real-time yields and performance for a given bond type and country.

**Endpoint:**  
`GET /bonds-spot`

**Request Parameters:**
- `api_key` (string, required)
- `region` (string, optional): e.g. "europe". Alternative to `country`.
- `country` (string, required unless `region` is used): e.g. "united_states"
- `type` (string, optional, defaults to "10y"): e.g. "10y", "6m", "30ytips"

**Example:**
```
GET /bonds-spot?api_key=YOUR_API_KEY&country=united_states&type=10y
```

**Response:**
```json
{
  "success": true,
  "code": 200,
  "message": "OK",
  "data": [
    {
      "bond_country": "united states",
      "bond_yield": 4.656,
      "bond_type": "10Y",
      "daily_bond_change": "0.0220",
      "weekly_bond_change_percent": "0.01%",
      "monthly_bond_change_percent": "0.00%",
      "yearly_bond_change_percent": "0.42%",
      "last_updated": "2026-08-26 15:10:46"
    }
  ]
}
```

---

### 3. 🕓 Historical Government Bond Yields

Get historical yields within a selected period (max 100 days).

**Endpoint:**  
`GET /bonds-history`

**Request Parameters:**
- `api_key` (string, required)
- `interval` (string, required): `day` or `month`
- `country` (string, required): e.g. "germany"
- `type` (string, required): e.g. "10y"
- `date_from` (optional): Format: YYYY-MM-DD
- `date_to` (optional)

**Example:**
```
GET /bonds-history?api_key=YOUR_API_KEY&country=united_states&type=10y&interval=day&date_from=2026-08-01&date_to=2026-08-10
```

**Response:**
```json
{
  "success": true,
  "code": 200,
  "message": "OK",
  "data": [
    { "date": "2026-08-10", "bond_type": "10Y", "yield": 4.713 },
    { "date": "2026-08-07", "bond_type": "10Y", "yield": 4.651 }
  ]
}
```

---

## 🚀 Why Choose FinanceFlowAPI?

✅ **Global Coverage**: 54 countries across the US, EU, and Asia  
💸 **Affordable Plans**: Test ($5/month, 200 requests), Standard ($25/month), Premium ($50/month)  
📦 **Clean JSON Format**: Ready for frontends, Python, Excel, JS, etc.  
📚 **Great Documentation**: Easy-to-use examples and clear endpoints  
🔮 **More Coming Soon**: SEC data and additional macro indicators

---

## 🧑‍💻 Get Started

1. **[Sign up](https://financeflowapi.com/create-account)** to get your API key  
2. **Test the endpoints** using the Test plan  
3. **Upgrade anytime** for more requests & deeper historical data  
4. **[View full docs](https://financeflowapi.com/api_documentation)** for more endpoints

---

## 🤝 Support

- 💌 support@financeflowapi.com  
- 🧭 [API Documentation](https://financeflowapi.com/api_documentation)  
- 🐛 Found an issue? Open one here on GitHub!

---

**FinanceFlowAPI**: Empowering fintech with real-time and historical financial data.
