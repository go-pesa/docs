# C2B Transactions(STK push)

> To start a transaction use this code:

```go

  client.StkPush(100,25412345678,"Refrence","Description")

/* Returns An StkResponse Object
type StkResponse struct {
  MerchantRequestID
  CheckoutRequestID
  ResponseCode
  ResultDesc
  ResponseDescription
  ResultCode
}
*/

```

This initializes a transaction. Payments are confirmed via callback or querying the transaction status. Store the CheckoutRequestID, it can be used to confirm the transaction status

<aside class="notice">
This <b>DOES NOT</b> charge the customer immediately, they still need to input their PIN and confirm. To confirm the transaction use the response from Safaricom sent to your <b>CALLBACK URL</b> or use the transaction query.
</aside>

# C2B Transaction Query(STK push query)

> To check a transaction's status use this code:

```go

  client.StkPushQuery("ws_CO_00000000000000000")

/* Returns An StkResponse Object
type StkResponse struct {
  MerchantRequestID
  CheckoutRequestID
  ResponseCode
  ResultDesc
  ResponseDescription
  ResultCode
}
*/

```

This checks a transaction by the CheckoutRequestID

<aside class="notice">
This should be initiated when the user should logically have completed the transaction.
</aside>