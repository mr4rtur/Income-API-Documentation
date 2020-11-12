# View Loan Investments

`[ID]` - you can use your `loan_id` or `income_loan_id`

```http
GET /loans/investment/[ID]?api_key=12345678901234567890123456789012'
```

## Error response

```json
{
  "success": false,
  "message": "Loan not found",
  "status_code": 404
}
```

## Success response

```json
{
  "success": true,
  "data": [
    {
      "investment_id": 101,
      "investor_id": 1,
      "loan_id": 100001,
      "loan_originator_id": 54,
      "investment_is_active": null,
      "investment_invest_amount": "20.00",
      "investment_interest_amount": null,
      "investment_received_amount": null,
      "investment_purchased_date": null,
      "investment_finished_date": null,
      "investment_currency": "EUR",
      "investment_market_id": 298,
      "created": "2020-11-09 08:21:29",
      "investment_moment_loan_saldo": "1100.00000",
      "investor_first_name": null,
      "investor_last_name": null
    }
  ]
}
```