# Post Bank Export Data

```http
POST '/loans/bank-transfer?api_key=12345678901234567890123456789012'
```

**Body**

```json
{
  "bankExportData": [
    {
      "transactions": [
        {
          "event_uuid": "2020102713534749764900-cd7eac39-4241-4d19-92c1-46f6fbae68e0",
          "amount": 331.22,
          "bankTransactionId": "1234567890",
          "transaction_date": "2020-10-01",
          "distribution": [
            {
              "amount": 300.22,
              "loan_distribution": {
                "interest": 44.1,
                "monthly_fee": 10,
                "capital": 246.12
              },
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
                      },
                      "prepayment_amount": 0
                    }
                  ],
                  "schedule_components": {
                    "capital": "principal",
                    "interest": "interest",
                    "capitalDebtInterest": "interest",
                    "monthly_fee": "interest"
                  }
               },
              "income_loan_ref": 100001,
              "type": "borrower repayment"
            }
          ],
          "optional_description": "For loan no 1088322",
          "optional_reference_number": 10883222,
          "optional_senderAccount": "032934023523402394",
          "optional_senderBank": "Bradesco",
          "optional_senderBankCode": "BR23AA",
          "optional_senderName": "Marguerita Consuela"
        }
      ]
    }
  ]
}
```

**Required parameters**

| Parameter | Type | Description |
| :--- | :--- | :--- |
| `transactions` | `array` | Transactions list |
| `transactions.*.amount` | `numeric` | Transaction amount |,
| `transactions.*.bankTransactionId` | `string` | Transaction ID from Bank (can be empty)|,
| `transactions.*.event_uuid` | `numeric` | Event UUID (Received from Income) |,
| `transactions.*.transaction_date` | `numeric` | Transaction date. Format: `Y-m-d` |,
| `transactions.*.distribution` | `array` | Distribution data |,
| `transactions.*.distribution.*.type` | `string` | Distribution type |,
| `transactions.*.distribution.*.income_loan_ref` | `numeric` | Loan ID |,
| `transactions.*.distribution.*.loan_schedule` | `array` | See [loan schedule description](./classificators/loan_schedule.md) |,
| `transactions.*.distribution.*.loan_distribution` | `array` | Loan distributions list |,
| `transactions.*.distribution.*.loan_distribution.interest` | `numeric` | Interest amount |,
| `transactions.*.distribution.*.loan_distribution.monthly_fee` | `numeric` | Monthly fee amount |,

**Note:** If `loan_schedule` have `prepayment_amount` - `schedule` and `schedule_components` is not required.

## Success response

```json
{
  "success": true,
  "data": {
    "message": "Transactions imported"
  }
}
```
