# Create Loan

```http
POST '/loans/store?api_key=12345678901234567890123456789012'
```

**Body**

```json
{
  "loan": {
    "loan_id": "223947",
    "apr": 576.46,
    "type": "SRT",
    "saldo": 2001.56,
    "period": 9,
    "status": "Current",
    "country": "BRA",
    "purpose": "Bills",
    "currency": "BRL",
    "due_date": "2020-12-07",
    "timezone": "America/Fortaleza",
    "list_date": "2020-11-06",
    "term_date": "2021-07-06",
    "debt_amount": 0,
    "issued_date": "2020-10-05",
    "list_amount": 4,
    "borrower_name": "Male, 20y",
    "interest_rate": 89,
    "issued_amount": 2000,
    "repaid_amount": 284.27,
    "schedule_type": "FULL",
    "skin_in_the_game": 4,
    "borrower_interest": 429.47,
    "buyback_guarantee": true,
    "extendable_schedule": true,
    "remaining_principal": 1926.66,
    "loan_schedule": {
      "schedule": [
        {
          "date": "2020-11-06",
          "rowno": 1,
          "repayment": {
            "total": 448.16,
            "repaid": true,
            "payments": [
              {
                "date": "2020-10-16",
                "amount": 448.16
              }
            ]
          },
          "schedule_components": {
            "capital": 132.28,
            "interest": 315.88,
            "capitalDebtInterest": 0
          }
        },
        {
          "date": "2020-12-07",
          "rowno": 2,
          "repayment": {
            "total": 439.06,
            "repaid": true,
            "payments": [
              {
                "date": "2020-10-16",
                "amount": 439.06
              }
            ]
          },
          "schedule_components": {
            "capital": 151.99,
            "interest": 287.07,
            "capitalDebtInterest": 0
          }
        }
      ],
      "schedule_components": {
        "capital": "principal",
        "interest": "interest",
        "capitalDebtInterest": "interest"
      }
    }
  }
}
```

**Required parameters**

| Parameter | Type | Description |
| :--- | :--- | :--- |
| `loan_id` | `string` | Your loan ID |,
| `country` | `string` | Country Code (see [countries list](./classificators/countries.md)) |,
| `type` | `string` | Loan type  (see [loan types list](./classificators/loan_types.md)) |,
| `currency` | `string` | Currency  (see [currencies list](./classificators/currencies.md)) |,
| `status` | `string` | Loan Status  (see [loan statuses list](./classificators/loan_statuses.md)) |,
| `issued_date` | `date` | Issued date. Format: `Y-m-d` |,
| `list_date` | `date` | List date. Format: `Y-m-d` |,
| `issued_amount` | `numeric` | Issued amount |,
| `list_amount` | `numeric` | List amount |,
| `skin_in_the_game` | `numeric` | |,
| `repaid_amount` | `numeric` | Repaid amount |,
| `debt_amount` | `numeric` | Debit amount |,
| `schedule_type` | `string` | Schedule Type  (see [schedule types list](./classificators/schedule_types.md)) |,
| `interest_rate` | `numeric` | Interest rate |,
| `apr` | `numeric` |  |,
| `extendable_schedule` | `boolean` | |,
| `purpose` | `string` | |,
| `buyback_guarantee` | `boolean` | Guarantee for buyback |,
| `saldo` | `numeric` | Saldo |,
| `remaining_principal` | `numeric` | |,
| `term_date` | `date` | Term date. Format: `Y-m-d` |,
| `due_date` | `date` | Due Date. Format: `Y-m-d` |,
| `borrower_name` | `string` | |,
| `period` | `numeric` | |,
| `borrower_interest` | `numeric` | |,
| `loan_schedule` | `array` | See [loan schedule description](./classificators/loan_schedule.md) |,
| `timezone` | `string` | Loan Timezone |,

## Success response

```json
{
  "success": true,
  "data": {
    "message": "Loan listed",
    "income_loan_id": 100001
  }
}
```