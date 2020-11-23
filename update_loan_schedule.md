# Update loan Schedule

`[ID]` - you can use your `loan_id` or `income_loan_ref`

```http
PATCH '/loans/update-schedule/[ID]?api_key=12345678901234567890123456789012'
```

**Body**

```json
{
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
       }
     ],
     "schedule_components": {
       "capital": "principal",
       "interest": "interest",
       "capitalDebtInterest": "interest"
     }
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