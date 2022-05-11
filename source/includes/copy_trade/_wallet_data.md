# t(:wallet)
t(:wallet_para)


### t(:cpyt_trade_wallet_balance)
> t(:codequote_curlExample)

```console
curl "https://api-testnet.bybit.com/derivatives/v3/copytrading/wallet/balance?api_key={api_key}&timestamp={timestamp}&sign={sign}"
```

```python--old
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Wallet.Wallet_getBalance().result())
```

```python--pybit
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com",
               api_key="", api_secret="")
print(session.get_wallet_balance())
```

> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "success",
    "result": {
    "availableBalance": "88881981.61301266",
      "usedMargin": "6463.81892229",
      "orderMargin": "6461.736762",
      "positionMargin": "2.08216029",
      "walletBalance": "88888445.43193495",
      "realisedPnl": "-444.061167",
      "unrealisedPnl": "6.948",
      "cumRealisedPnl": "-442.56806505",
      "coin": "USDT",
      "equity": "88888452.37993495"
  }
}
```

t(:cpyt_trade_wallet_balance)


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpwBalance>/derivatives/v3/copytrading/wallet/balance</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpwBalance"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |



<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|<a href="#currency-currency-coin">coin</a> |false |string |t(:row_comment_coin) |
|equity |number |t(:row_comment_equity)  |
|available_balance |number |t(:row_comment_available_balance)  |
|used_margin |number |t(:row_comment_used_margin)    |
|order_margin|number |t(:row_comment_order_margin)    |
|position_margin |number |t(:row_comment_position_margin)  |
|wallet_balance |number |t(:row_comment_wallet_balance)  |
|realised_pnl |number |t(:row_comment_realised_pnl)  |
|unrealised_pnl |number |t(:row_comment_unrealised_pnl)  |
|cum_realised_pnl|number |t(:row_comment_cum_realised_pnl)  |



### t(:cpyt_trade_wallet_transfer)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/derivatives/v3/copytrading/wallet/transfer \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","transfer_id":"5f95de18-b10f-43be-9746-7b95c4a37d97","coin":"USDT","amount":"88.88","fromAccountType":"CONTRACT","toAccountType":"COPYTRADING","timestamp":{timestamp},"sign":"{sign}"}'

```

```python--old
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Order.Order_new(transfer_id="5f95de18-b10f-43be-9746-7b95c4a37d97",coin="USDT",amount="Market",fromAccountType="CONTRACT",toAccountType="COPYTRADING").result())
```

```python--pybit
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com",
               api_key="", api_secret="")
print(session.place_active_order(
    transfer_id="5f95de18-b10f-43be-9746-7b95c4a37d97",
    coin="USDT",
    amount="Market",
    fromAccountType="CONTRACT",
    toAccountType="COPYTRADING"
))
```

> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "success",
    "result": {
    "transferId": "5f95de18-b10f-43be-9746-7b95c4a37d97"
  }
}
```

t(:cpyt_trade_wallet_transfer)



<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=oawwListNew>/derivatives/v3/copytrading/wallet/transfer</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oawwListNew"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|transfer_id |<b>true</b> |string |t(:row_comment_transfer_id) |
|<a href="#currency-currency-coin">coin</a> |<b>true</b> |string |t(:row_comment_currency) |
|amount |<b>true</b> |string |t(:row_comment_to_amount) |
|<a href="#account-type-from_account_type-to_account_type">from_account_type</a> |<b>true</b> |string |t(:row_comment_accounttype) |
|<a href="#account-type-from_account_type-to_account_type">to_account_type</a> |<b>true</b> |string |t(:row_comment_accounttype) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|transfer_id |string |t(:row_comment_transfer_id) |


