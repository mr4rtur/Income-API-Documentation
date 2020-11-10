# Update loan Schedule

`[ID]` - you can use your `loan_id` or `income_loan_id`

```http
PATCH '/loans/update-schedule/[ID]?api_key=12345678901234567890123456789012'
```

**Body**

```json
{
  "loan_schedule": {
      "schedule_components": {
          "capital": "principal",
          "interest": "interest",
          "capitalDebInterest": "interest"
      },
      "schedule": [{
          "rowno": 1,
          "date": "2020-09-03",
          "schedule_components": {
              "capital": 200.11,
              "interest": 2.21,
              "capitalDebInterest": 11.01
          },
          "repayment": {
              "total": 213.33,
              "repaid": true,
              "payments": [{
                  "date": "2020-09-01",
                  "amount": 213.33
              }]
          }
      }]
  }
}
```


**Required parameters**

See [loan schedule description](./classificators/loan_schedule.md)

## Success response

```json
{
  "success": true,
  "data": "Loan schedule updated"
}
```