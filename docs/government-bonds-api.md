
# 🇺🇸 Government Bonds API — Real-Time & Historical Bond Yields

The **Government Bonds API** from [FinanceFlowAPI](https://financeflowapi.com) provides real-time and historical bond yield data for major economies including the **United States**, **Germany**, **Australia**, and more.

📈 Ideal for:
- Investors & traders
- Financial analysts
- Research platforms
- Fintech & macroeconomic tools

Integrate seamless, accurate bond yield data into your dashboards or apps with **just a few lines of code**.

---

## 🌐 Base URL

```
https://financeflowapi.com/api/v1/
```

---

## 📘 API Endpoints

### 1. ✅ Supported Countries List

Retrieve a list of countries with available bond data.

**Endpoint:**  
`GET /bonds-catalog`

**Request Parameters:**
- `api_key` (string, required) – Your API key.

**Example:**
```
GET /bonds-catalog?api_key=YOUR_API_KEY
```

**Response:**
```json
{
  "success": true,
  "data": [
    { "bond_country": "australia" },
    { "bond_country": "austria" }
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
- `region` (string, optional) — e.g. "europe"
- `country` (string, required) — e.g. "united_states"
- `type` (string, required) — e.g. "10y", "6m", "30ytips"

**Example:**
```
GET /bonds-spot?api_key=YOUR_API_KEY&country=united_states&type=10y
```

**Response:**
```json
{
  "data": [
    {
      "bond_country": "united states",
      "bond_yield": 4.215,
      "bond_type": "10Y",
      "daily_bond_change": "0.0500",
      "weekly_bond_change_percent": "-0.22%",
      "monthly_bond_change_percent": "-0.33%",
      "ytd_bond_value_change": "-0.36%",
      "yearly_bond_change_percent": "-0.04%",
      "last_updated": "2024-09-11 21:22:12"
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
- `frequency` (string, required) — `day` or `month`
- `country` (string, required) — e.g. "germany"
- `type` (string, required) — e.g. "10y"
- `date_from` (optional) — Format: YYYY-MM-DD
- `date_to` (optional)

**Example:**
```
GET /bonds-history?api_key=YOUR_API_KEY&country=united_states&type=10y&frequency=day&date_from=2025-01-01&date_to=2025-01-31
```

**Response:**
```json
{
  "data": [
    { "date": "2025-01-31", "bond_type": "10y", "price": 4.541 },
    { "date": "2025-01-30", "bond_type": "10y", "price": 4.519 }
  ]
}
```

---

## 🚀 Why Choose FinanceFlowAPI?

✅ **Global Coverage** – US, EU, Asia  
💸 **Affordable Plans** – Test (200 req/month, only 5$), Standard ($25), Premium ($50)  
📦 **Clean JSON Format** – Ready for frontends, Python, Excel, JS, etc.  
📚 **Great Documentation** – Easy-to-use examples and clear endpoints  
🔮 **More Coming Soon** – SEC data, bond candles, and macro indicators

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

**FinanceFlowAPI** — Empowering fintech with real-time and historical financial data.
