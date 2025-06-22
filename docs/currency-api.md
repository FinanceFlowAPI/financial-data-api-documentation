# Currency API - Real-Time Currency Pair Data

The **Currency API** provides real-time currency pair data for forex trading and financial applications. Access up-to-date exchange rates for pairs like CHF/EUR, USD/JPY, and more, with updates every 1-3 minutes. This API is ideal for developers building forex platforms, financial dashboards, or trading bots. Explore the open-source documentation and integrate real-time currency data today.

## Base URL

```
https://financeflowapi.com/api/v1/
```

All endpoints follow this base URL.

## Authentication

All requests require a valid `api_key`. Sign up at [FinanceFlowAPI Create Account](https://financeflowapi.com/create-account/) to get a free API key with 200 requests per month. Higher limits are available with Standard ($10.99/month) or Premium ($20.99/month) plans.

## Endpoints

### 1. Currency Pairs Catalog

**Endpoint:** `/currency-catalog`

**Description:** Retrieves a list of all supported currency pairs or filters pairs by a specific currency (e.g., USD, EUR). Perfect for discovering available forex pairs for trading or analysis.

**HTTP Method:** GET

**Request Parameters:**

| Parameter   | Type   | Required | Description                                      |
|-------------|--------|----------|--------------------------------------------------|
| `api_key`   | String | Yes      | Your unique API key.                             |
| `currency`  | String | No       | Currency code to filter pairs (e.g., "USD").      |

**Request Examples:**

- **All currency pairs:**
  ```
  GET https://financeflowapi.com/api/v1/currency-catalog?api_key=YOUR_API_KEY
  ```

- **Filter by currency (USD):**
  ```
  GET https://financeflowapi.com/api/v1/currency-catalog?api_key=YOUR_API_KEY&currency=USD
  ```

**Response Example:**

```json
{
    "success": true,
    "code": 200,
    "message": "OK",
    "meta": {
        "timestamp": 1750598697,
        "request_id": "685804293fa96"
    },
    "data": [
        {"pair": "AED/CHF"},
        {"pair": "AUD/CHF"},
        {"pair": "BRL/CHF"},
        {"pair": "CAD/CHF"},
        ...
    ]
}
```

### 2. Real-Time Currency Pair Data

**Endpoint:** `/currency-spot`

**Description:** Provides real-time exchange rate data for a specific currency pair (e.g., CHF/EUR) or all pairs associated with a given currency (e.g., USD). Data updates every 1-3 minutes, making it ideal for real-time forex trading applications.

**HTTP Method:** GET

**Request Parameters:**

| Parameter   | Type   | Required | Description                                                  |
|-------------|--------|----------|--------------------------------------------------------------|
| `api_key`   | String | Yes      | Your unique API key.                                         |
| `pair`      | String | No       | Currency pair (e.g., "CHF/EUR"). Use either `pair` or `currency`. |
| `currency`  | String | No       | Currency code to retrieve all related pairs (e.g., "USD").   |

**Note:** You must provide either `pair` or `currency`, but not both.

**Request Examples:**

- **By currency pair (CHF/EUR):**
  ```
  GET https://financeflowapi.com/api/v1/currency-spot?api_key=YOUR_API_KEY&pair=CHF/EUR
  ```

- **By currency (USD):**
  ```
  GET https://financeflowapi.com/api/v1/currency-spot?api_key=YOUR_API_KEY&currency=USD
  ```

**Response Examples:**

- **By currency pair (CHF/EUR):**

```json
{
    "success": true,
    "code": 200,
    "message": "OK",
    "meta": {
        "timestamp": 1750596763,
        "request_id": "6857fc9b44fe0"
    },
    "data": [
        {
            "pair": "CHF/EUR",
            "bid": "1.0600",
            "ask": "1.0614",
            "high": "1.0660",
            "low": "1.0596",
            "chg": "-0.0046",
            "chg_percent": "-0.43%",
            "last_update": "2025-06-21 23:59:51"
        }
    ]
}
```

- **By currency (USD):**

```json
{
    "success": true,
    "code": 200,
    "message": "OK",
    "meta": {
        "timestamp": 1750598906,
        "request_id": "685804fac0b16"
    },
    "data": [
        {
            "pair": "ADA/USD",
            "bid": "0.5576",
            "ask": "0.5578",
            "high": "0.5578",
            "low": "0.5571",
            "chg": "0.0007",
            "chg_percent": "0.13%",
            "last_update": "2025-06-22 00:00:30"
        },
        {
            "pair": "AED/USD",
            "bid": "0.2723",
            "ask": "0.2723",
            "high": "0.2723",
            "low": "0.2722",
            "chg": "0.0000",
            "chg_percent": "0%",
            "last_update": "2025-06-21 23:59:15"
        },
        {
            "pair": "ALG/USD",
            "bid": "0.1632",
            "ask": "0.1638",
            "high": "0.1691",
            "low": "0.1572",
            "chg": "-0.0046",
            "chg_percent": "-2.75%",
            "last_update": "2025-06-22 00:00:30"
        },
        ...
    ]
}
```

## Code Examples

### Python Example (Real-Time Currency Pair Data)

```python
import requests

API_KEY = 'your_api_key'
url = f'https://financeflowapi.com/api/v1/currency-spot?api_key={API_KEY}&pair=CHF/EUR'

response = requests.get(url)
data = response.json()

print(data)
```

### JavaScript Example (Real-Time Currency Pair Data)

```javascript
const API_KEY = 'your_api_key';
const url = `https://financeflowapi.com/api/v1/currency-spot?api_key=${API_KEY}&pair=CHF/EUR`;

fetch(url)
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

### PHP Example (Real-Time Currency Pair Data)

```php
<?php
$api_key = 'your_api_key';
$url = "https://financeflowapi.com/api/v1/currency-spot?api_key=$api_key&pair=CHF/EUR";

$response = file_get_contents($url);
$data = json_decode($response, true);

print_r($data);
?>
```

## Rate Limits

- **Free Plan:** 200 requests per month.
- **Standard Plan:** $10.99/month (higher limits).
- **Premium Plan:** $20.99/month (highest limits).

Check your rate limits in your account dashboard at [FinanceFlowAPI My Account](https://financeflowapi.com/my-account/).

## Conclusion

The **Currency API** empowers developers with real-time currency pair data for forex trading, financial analysis, and more. Integrate this API to access exchange rates for thousands of currency pairs with updates every 1-3 minutes. Get started with a free API key at [FinanceFlowAPI Create Account](https://financeflowapi.com/create-account/) and explore our open-source documentation on [GitHub](https://github.com/FinanceFlowAPI/financial-data-api-documentation). Star our repo to stay updated with the latest financial data API features!