# Buyback Loan

```http
POST '/loans/buyback?api_key=12345678901234567890123456789012'
```

**Body**

```json
{
    "income_loan_ref": 100040,
    "reason": "repaid"
}
```

## Success response

See [view loan result](./view_loan.md)

**Required parameters**

| Parameter | Type | Description |
| :--- | :--- | :--- |
| `income_loan_ref` | `numeric` | Income loan ref number |,
| `reason` | `string` | buyback reason (see [buyback reasons](./classificators/buyback_reasons.md)) |
