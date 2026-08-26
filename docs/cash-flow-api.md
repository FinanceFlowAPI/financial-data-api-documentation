# Stock Ticker Cash Flow API - Quarterly & Annual Financials with FinanceFlowAPI

The **Cash Flow API** from [FinanceFlowAPI](https://financeflowapi.com) provides quarterly and annual cash flow statement data (operating, investing, and financing cash flow, free cash flow, capital expenditure, and more) for any of our **511,000+ stock tickers**. Built for fundamental analysts, valuation models, and screening tools.

[Sign up](https://financeflowapi.com/create-account/) to get started and explore the full API at [financeflowapi.com/api_documentation](https://financeflowapi.com/api_documentation).

## Base URL
```
https://financeflowapi.com/api/v1/
```

## Endpoint

### Cash Flow
- **Endpoint**: `/ticker-cash-flow`
- **Description**: Retrieves cash flow statement line items for a specific stock ticker, for the last 5 quarterly or 5 annual reporting periods.

#### Request Parameters
- `api_key` (string, required): Your unique API key.
- `ticker` (string, required): The stock ticker symbol (e.g., "AAPL").
- `type` (string, optional, default `quarterly_report`): `quarterly_report` or `annual_report`.
- `date_from` (string, optional): Start date in YYYY-MM-DD format, filters returned periods by report date. Must be provided together with `date_to`.
- `date_to` (string, optional): End date in YYYY-MM-DD format. Must be provided together with `date_from`.

**Notes:**
- The difference between `date_from` and `date_to` must not exceed 3650 days (10 years). Future dates are not allowed.
- How far back you can query is governed by your plan's historical data allowance, see [Pricing Plans](../README.md#-pricing-plans).
- Any `type` value other than `quarterly_report`/`annual_report` is silently treated as `quarterly_report` by the underlying data source, but the response's `meta.period_type ` field will echo back whatever value you sent. Only rely on `quarterly_report`/`annual_report`.
- The `meta` object's period field is literally named `"period_type "`, with a trailing space, in the JSON response. Access it exactly as returned (e.g. `response['meta']['period_type ']`), not `period_type`.

#### Request Example
```
GET https://financeflowapi.com/api/v1/ticker-cash-flow?api_key=YOUR_API_KEY&ticker=AAPL&type=annual_report
```

#### Response Example
```json
{
    "success": true,
    "code": 200,
    "message": "OK",
    "meta": {
        "ticker": "AAPL",
        "statement_type": "CashFlow",
        "period_type ": "annual_report",
        "timestamp": 1787758784,
        "request_id": "6a8f08c0c6206"
    },
    "data": [
        {
            "date": "2025-09-30",
            "BEGINNING_CASH_POSITION": "29943000000",
            "END_CASH_POSITION": "35934000000",
            "OPERATING_CASH_FLOW": "111482000000",
            "INVESTING_CASH_FLOW": "15195000000",
            "FINANCING_CASH_FLOW": "-120686000000",
            "CAPITAL_EXPENDITURE": "-12715000000",
            "FREE_CASH_FLOW": "98767000000",
            "CASH_DIVIDENDS_PAID": "-15421000000",
            "REPURCHASE_OFCAPITAL_STOCK": "-90711000000"
        }
    ]
}
```

The full response includes additional line items such as `DEPRECIATION_AND_AMORTIZATION`, `STOCK_BASED_COMPENSATION`, `CHANGE_INWORKING_CAPITAL`, `ISSUANCE_OFDEBT`, `LONG_TERM_DEBT_PAYMENTS`, `INCOME_TAX_PAID_SUPPLEMENTAL_DATA`, and other Yahoo Finance-style, ALL_CAPS_WITH_UNDERSCORES field names. Not every field is populated for every ticker or period.

#### Errors
| Code | When | Message |
|------|------|---------|
| 400 | `ticker` missing | `required parameters not found, please specify one of: [ticker]` |
| 400 | only one of `date_from`/`date_to` provided | `Both date_from and date_to must be provided.` |
| 400 | invalid date format | `Invalid date format. Please use YYYY-MM-DD.` |
| 400 | date range exceeds 3650 days | `Invalid date range. The difference between date_from and date_to must not exceed 3650 days.` |
| 400 | `date_from`/`date_to` in the future | `Future dates are not allowed.` |
| 400 | date range exceeds your plan's historical data allowance | `Your plan allows access to historical data for the last N days only` |
| 404 | `ticker` not found, or no report matches the given date range | `Data not found, please check your request.` |

## Why Choose FinanceFlowAPI?
- **Deep Ticker Coverage**: Cash flow data for any of our 511,000+ stock tickers.
- **Quarterly & Annual**: Switch between reporting periods with a single `type` parameter.
- **Affordable Plans**: Start with our [Test plan](https://financeflowapi.com/create-account/) ($5/month, 200 requests) or upgrade to Standard ($25/month) or Premium ($50/month).
- **Clear Documentation**: Request/response examples and a full error reference for every endpoint.

## Get Started
1. [Sign up](https://financeflowapi.com/create-account/) to get your API key.
2. Explore the [FinanceFlowAPI documentation](https://financeflowapi.com/api_documentation/) or this repository for details.
3. Test the endpoint with our Test plan or unlock a longer historical window with a paid plan.

Star this repository to support FinanceFlowAPI and stay updated on new features! For questions, open an [issue](https://github.com/FinanceFlowAPI/api-documentation/issues) or contact [support@financeflowapi.com](mailto:support@financeflowapi.com).

---
*FinanceFlowAPI: Empowering fintech with real-time and historical financial data.*
