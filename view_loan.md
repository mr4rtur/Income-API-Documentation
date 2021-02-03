# View Loan

```http
GET /loans/view/[INCOME_LOAN_REF]?api_key=12345678901234567890123456789012'
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

Attributes description - [create loan request](./create_loan.md)

```json
{
  "success": true,
  "data": {
    "income_loan_ref": 100014,
    "type": "SRT",
    "country": "",
    "schedule_type": "",
    "cashflow_type": "",
    "investor_interest_rate": "89.00000",
    "apr": "576.460",
    "skin_in_the_game": 4,
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
    },
    "currency": "BRL",
    "status": "Current",
    "issued_date": "2020-10-05",
    "list_datetime": "2020-11-10 13:49:09",
    "issued_amount": "2000.00",
    "repaid_amount": "284.27",
    "debt_amount": "0.00",
    "extendable_schedule": 1,
    "purpose": "Bills",
    "buyback_guarantee": 1,
    "paid_out_date": null,
    "due_date": "2020-12-07",
    "borrower_name": "Male, 20y",
    "period": 9,
    "borrower_interest": "429.47000",
    "timezone": "America\/Fortaleza",
    "created": "2020-11-10 13:49:09"
  }
}
```
