# Postback on Income events

Income system can notify LO on certain events with GET request concerning LO loans:
* Loan gets investment
* Loan gets forced buyback event
* System detects incoming payment from LO for distribution

# Setup

For configuring the postback, LO must provide the postback URL (f.e. `https://api.loanoriginator.com/postback/income`)

# Parameters

We add following parameters to the URL:
* Loan gets investment: `event=investment&income_loan_ref={INCOME_LOAN_REF}`
* Loan gets forced buyback event: `event=buyback&income_loan_ref={INCOME_LOAN_REF}`
* System detects incoming payment from LO for distribution: `event=banktransfer&event_uuid={EVENT_UUID}`

Example combined URL

```http
https://api.loanoriginator.com/postback/income?event=investment&income_loan_ref=20002433
https://api.loanoriginator.com/postback/income?event=banktransfer&event_uuid=2020102713534746878700-1f7444d0-ed97-4bec-a4ea-79c562f703ca
```

# Response to postback request

Successful result status code 200 is expected. Although if the result is anything else, request won't be repeated. The request is sent only once.
