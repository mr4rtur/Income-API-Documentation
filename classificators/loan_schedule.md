```json
{
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
```

**Required parameters**

| Parameter | Type | Description |
| :--- | :--- | :--- |
| `schedule` | `array` | Schedule data |,
| `schedule_components` | `array` | Schedule components list |,
| `schedule.*.date` | `date` | Schedule date. Format: `Y-m-d` |,
| `schedule.*.rowno` | `numeric` | Schedule rowno # |,
| `schedule.*.repayment` | `array` | Repayment amounts |,
| `schedule.*.repayment.total` | `numeric` | Repayment total amount |,
| `schedule.*.repayment.repaid` | `boolean` | Repayment repaid (`true`/`false`) |,
| `schedule.*.repayment.schedule_components` | `boolean` | Repayment schedule components amounts |,
| `schedule.*.repayment.payments` | `array` | Payments info, required only if repaid: true |,
| `schedule.*.repayment.payments.*.date` | `date` | Payment date. Format: `Y-m-d` |,
| `schedule.*.repayment.payments.*.amount` | `numeric` | Payment amount |,
