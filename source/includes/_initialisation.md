# Initialisation

> To initialize the go-pesa client, use this code:

```go
import "github.com/go-pesa/go-pesa"


  //To use Safaricom's default credentials (For development)
  client := gopesa.New("CONSUMER_SECRET","CONSUMER_KEY")

  //To use Production Credentials
  client := gopesa.New("CONSUMER_SECRET",
                       "CONSUMER_KEY",
                       gopesa.ShortCode(0000), //LIPA NA M-PESA SHORTCODE
                       gopesa.MSISDN(254712345678), //Phone Nummber for Transactions given by Safaricom
                       gopesa.PassKey("PASS_KEY"), //PassKey given by Safaricom
                       gopesa.TransactionCallback("https://mydomain/mycallbackpath"), //URL for Safaricom to confirm transactions
                       gopesa.ProductionURL("https://myproductionurl"), //Production URL given by Safaricom
                       )


```

> This creates a Client 'object' that automatically performs authorisation and allows for transactions. Multiple clients can be created within a single application. Each client manages it's own credentials and cache separately.

Make sure to replace all the arguments with credentials from Safarricom's website. You can register for a new account and credentials at safaricom's [developer portal](http://developer.safaricom.co.ke). The credentials should be similar to these [test credentials](https://developer.safaricom.co.ke/test_credentials).

<aside class="notice">
When testing you must replace <code>CONSUMER_SECRET</code> and <code>CONSUMER_KEY</code> with your own for it work. For production all the parameters must be filled to allow for a basic C2B transaction.
</aside>