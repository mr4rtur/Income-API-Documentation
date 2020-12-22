# View Bank Transactions

Show bank transactions in a period:
`Date from` and `Date to` format: `Y-m-d`

```http
GET /loans/bank-transfer?api_key=12345678901234567890123456789012&date_from=2019-01-01&date_to=2020-12-12
```

Show bank transactions by `event_uuid`:
```http
GET /loans/bank-transfer?api_key=12345678901234567890123456789012&event_uuid=2020120411351804896600-1aebddec-0402-4e59-988b-038213edc23c
```

## Success response

```json
{
  "success": true,
  "data": [
    {
      "event_uuid": "2020102713534746878700-1f7444d0-ed97-4bec-a4ea-79c562f703ca",
      "amount": 20385.92,
      "description": "LIQUIDACAO DE COBRANCA Valor Disponivel",
      "currency": "BRL",
      "transaction_date": "2020-12-01",
      "bankTransactionId": "4006026"
    },
    {
      "event_uuid": "2020102713534749764900-cd7eac39-4241-4d19-92c1-46f6fbae68e0",
      "amount": 387.86,
      "description": "DOC CREDITO AUTOMATICO* SANDRA RIBEIRO",
      "currency": "EUR",
      "transaction_date": "2020-12-01",
      "bankTransactionId": "743231"
    }
  ]
}
```
