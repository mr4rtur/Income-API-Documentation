# View Loan List

```http
GET /loans/list/?api_key=12345678901234567890123456789012'
```

## Success response

Array of Loans [view loan request](./view_loan.md)

```json
{
  "success": true,
  "data": [
    {loan_data},
    {loan2_data},
    ...
  ]
}
```