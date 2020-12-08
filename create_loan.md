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
    "period": 9,
    "status": "Current",
    "country": "BRA",
    "purpose": "Bills",
    "currency": "BRL",
    "due_date": "2020-12-07",
    "timezone": "America/Fortaleza",
    "list_date": "2020-11-06",
    "debt_amount": 0,
    "issued_date": "2020-10-05",
    "borrower_name": "Male, 42y",
    "investor_interest_rate": 10,
    "issued_amount": 2000,
    "repaid_amount": 284.27,
    "schedule_type": "FULL",
    "skin_in_the_game": 20,
    "borrower_interest": 89.47,
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
| `loan_id` | `string` | Loan Originator loan ID. |,
| `country` | `string` | Country Code (see [countries list](./classificators/countries.md)) |,
| `type` | `string` | Loan type  (see [loan types list](./classificators/loan_types.md)) |,
| `currency` | `string` | Currency  (see [currencies list](./classificators/currencies.md)) |,
| `status` | `string` | Loan Status  (see [loan statuses list](./classificators/loan_statuses.md)) |,
| `issued_date` | `date` | Issued date. Format: `Y-m-d`. Loan original issuance to Borrower. |,
| `list_date` | `date` | Loan listing date to the platform. Format: `Y-m-d`.  |,
| `issued_amount` | `numeric` | Amount issued to the Borrower. |,
| `remaining_principal` | `numeric` | Principal balance during loan listing. |,
| `skin_in_the_game` | `numeric` | Skin In The Game %. Percentage of the principal whichi no investment can be made. Percentage range is agreed with Loan Originator in the contract. |,
| `repaid_amount` | `numeric` | Repaid amount until listing moment. |,
| `debt_amount` | `numeric` | Debt amount at the listing moment. |,
| `schedule_type` | `string` | Schedule Type  (see [schedule types list](./classificators/schedule_types.md)) |,
| `investor_interest_rate` | `numeric` | Interest rate offered to Investros by Loan Originator. |,
| `apr` | `numeric` | Loan Annual Percentage Rate based on 365-day year. |,
| `extendable_schedule` | `boolean` | Mark 'true' if Borrower contract allows extending of the schedule, 'false' if not allowed. |,
| `purpose` | `string` | Purpose of the loan in short (up to 255 chars). |,
| `buyback_guarantee` | `boolean` | Guarantee for buyback. Mark 'true' if Loan Originator will buy back investments when loans goes over 60 DPD (Days Past Due). |,
| `due_date` | `date` | Loan Due Date. Format: `Y-m-d` |,
| `borrower_name` | `string` | Name of the borrower if allowed. Can be Sex and age, f.e. "Male 42y". |,
| `period` | `numeric` | Original loan duration in months. If < 1month , then 1. |,
| `borrower_interest` | `numeric` | Original loan Borrower yearly based interest. |,
| `loan_schedule` | `array` | See [loan schedule description](./classificators/loan_schedule.md) |,
| `timezone` | `string` | Loan Originator Timezone in TZ Database (https://www.iana.org/time-zones) format. f.e. "America/Sao_Paulo". |,

## Success response

```json
{
  "success": true,
  "data": {
    "message": "Loan listed",
    "income_loan_ref": 100001
  }
}
```
