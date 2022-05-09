# t(:accountdata)
t(:account_para)

## t(:copy_trade_order)
### t(:copy_trade_create_order)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/derivatives/v3/copytrading/order/create \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","side":"Buy","symbol":"BTCUSDT","order_type":"Market","qty":"10","timestamp":{timestamp},"sign":"{sign}"}'

```

```python--old
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Order.Order_new(side="Buy",symbol="BTCUSDT",order_type="Market",qty="10").result())
```

```python--pybit
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com",
               api_key="", api_secret="")
print(session.place_active_order(
    symbol="BTCUSDT",
    side="Buy",
    order_type="Market",
    qty="10",
))
```


> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "success",
    "result": {
    "orderId": "419190fe-016c-469a-810e-936bef2f5d59",
      "orderLinkId": "234590fe-016c-44f6-fg78-936b44556ygg"
  }
}
```

t(:copy_trade_create_order)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/derivatives/v3/copytrading/order/create</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_side) |<b>true</b> |string |t(:row_comment_side)    |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)   |
|t(:row_parameter_order_type) |<b>true</b> |string |t(:row_comment_activeOrderType)   |
|t(:row_parameter_quantity) |<b>true</b> |string |t(:row_comment_qty) |
|t(:row_parameter_price) |<b>true</b> |string |t(:row_comment_resp_price) |
|order_link_id |false |string |t(:row_comment_orderLinkId) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| order_id |string |t(:row_comment_order_id) |
|order_link_id |string |t(:row_comment_orderLinkId)  |


### t(:copy_trade_order_list)
> t(:codequote_curlExample)

```console
curl "https://api-testnet.bybit.com/derivatives/v3/copytrading/order/list?api_key={api_key}&timestamp={timestamp}&sign={sign}&symbol=ETHUSDT"
```

```python--old
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Order.Order_getOrders(symbol="ETHUSDT").result())
```

```python--pybit
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com",
               api_key="", api_secret="")
print(session.get_active_order(
    symbol="ETHUSDT",
))
```

> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "success",
    "result": {
    "list": [
      {
        "orderId": "ae0700f6-c990-4de5-9d6e-0fdf8d5aabea",
        "symbol": "ETHUSDT",
        "orderLinkId": "234500f6-c45f-4de5-9d6e-0fft67htr34",
        "side": "Sell",
        "copyTradeOrderStatus": "New",
        "price": "4000.00",
        "qty": "5.55",
        "timeInForce": "GoodTillCancel",
        "leavesQty": "5.55",
        "isIsolated": true,
        "leavesValue": "22200",
        "leverage": "44",
        "cumExecValue": "0",
        "cumExecFee": "0",
        "createdTime": "1652216213331",
        "updatedTime": "1652216213365"
      }
    ]
  }
}
```

t(:copy_trade_order_list)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpoList>/derivatives/v3/copytrading/order/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |false |string |t(:row_comment_symbol) |
|order_id |false |string ||
|order_link_id |false |string | |
|copy_trade_order_type |false |string | |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|list |object[] | |
|orderId |string |t(:account_row_comment_orderId) |
|orderLinkId |string |t(:row_comment_orderLinkId)  |
|symbol |string |t(:row_comment_symbol) |
|side |string |t(:row_comment_side) |
|price  |string |t(:row_comment_resp_price) |
|qty  |string |t(:row_response_comment_qty) |
|timeInForce |string |t(:row_comment_timeInForce)  |
|isIsolated |string |t(:row_comment_isolated) |
|leverage |string |t(:resp_field_leverage) |
|copyTradeOrderStatus |string |t(:copy_trade_row_comment_order_type) |
|leavesQty |string |t(:row_comment_leaves_qty) |
|leavesValue |string |t(:row_comment_leaves_value) |
|cumExecValue |string |t(:linear_resp_field_cum_exec_value)  |
|cumExecFee |string |t(:linear_resp_field_cum_exec_fee)  |
|createdTime |string |t(:row_comment_created_at)  |
|updatedTime |string |t(:row_comment_updated_at)  |

### t(:copy_trade_cancel_order)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/derivatives/v3/copytrading/order/cancel \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSDT","order_id":"419190fe-016c-469a-810e-936bef2f5d59","timestamp":{timestamp},"sign":"{sign}"}'
```

```python--old
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Order.Order_cancel(symbol="BTCUSDT", order_id="419190fe-016c-469a-810e-936bef2f5d59").result())
```

```python--pybit
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com",
               api_key="", api_secret="")
print(session.cancel_active_order(
    symbol="BTCUSDT",
    order_id="419190fe-016c-469a-810e-936bef2f5d59"
))
```


> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "success",
    "result": {
    "orderId": "419190fe-016c-469a-810e-936bef2f5d59",
      "orderLinkId": ""
  }
}
```

t(:copy_trade_cancel_order)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCancel>/derivatives/v3/copytrading/order/cancel</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCancel"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>

|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|order_id |false |string |t(:misc_row_comment_orderIdNotOrderLinkId) |
|order_link_id |false |string |t(:misc_row_comment_orderLinkIdNotOrderId) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|order_id |string |t(:account_row_comment_orderId) |
|order_link_id |string |t(:row_comment_orderLinkId)  |


### t(:copy_trade_close_order)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/derivatives/v3/copytrading/order/close \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSDT","order_id":"419190fe-016c-469a-810e-936bef2f5d59","timestamp":{timestamp},"sign":"{sign}"}'
```

```python--old
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Order.Order_cancelAll(symbol="BTCUSD",order_id=""order_id":"419190fe-016c-469a-810e-936bef2f5d59").result())
```

```python--pybit
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com",
               api_key="", api_secret="")
print(session.cancel_all_active_orders(
    symbol="BTCUSD",
    order_id=""order_id":"419190fe-016c-469a-810e-936bef2f5d59"
))
```

> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "success",
    "result": {
    "orderId": "419190fe-016c-469a-810e-936bef2f5d59",
      "orderLinkId": ""
  }
}
```

t(:copy_trade_close_order)

<aside class="notice">
t(:account_aside_cancelAllActive)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCancelAll>/derivatives/v3/copytrading/order/close</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCancelAll"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |false |string |t(:row_comment_symbol)   |
|order_link_id |false |string |t(:row_comment_orderLinkId) |
|parent_order_id |false |string |t(:copy_trade_row_comment_parentOrderIdNotparentOrderLinkId) |
|parent_order_link_id |false |string |t(:copy_trade_row_comment_parentOrderLinkIdNotOrderId) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|user_id |string |t(:row_comment_userID)  |
|user_link_id |number |t(:row_comment_orderLinkId)  |


## t(:position)
### t(:copy_trade_positon_list)
> t(:codequote_curlExample)

```console
curl "https://api-testnet.bybit.com/derivatives/v3/copytrading/position/list?api_key={api_key}&symbol=XRPUSDT&timestamp={timestamp}&sign={sign}"
```

```python--old
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Positions.Positions_myPosition(symbol="XRPUSDT").result())
```

```python--pybit
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com",
               api_key="", api_secret="")
print(session.my_position(
    symbol="XRPUSDT"
))
```

> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "success",
    "result": {
    "data": [
      {
        "symbol": "XRPUSDT",
        "side": "Buy",
        "size": "4",
        "positionValue": "3.28",
        "entryPrice": "0.82",
        "liqPrice": "0.0001",
        "bustPrice": "0.0001",
        "markPrice": "0.5047",
        "leverage": "10",
        "isIsolated": false,
        "positionMargin": "0.0415737",
        "occClosingFee": "0.0000003",
        "occFundingFee": "0",
        "cumRealisedPnl": "-0.36682",
        "freeQty": "-4",
        "unrealisedPnl": "-1.2612",
        "positionIdx": "1",
        "createdTime": "1651594009009",
        "updatedTime": "1652223355185"
      },
      {
        "symbol": "XRPUSDT",
        "side": "Sell",
        "size": "28",
        "positionValue": "22.6984",
        "entryPrice": "0.81065714",
        "liqPrice": "199.9998",
        "bustPrice": "199.9998",
        "markPrice": "0.5047",
        "leverage": "10",
        "isIsolated": false,
        "positionMargin": "88881979.32381973",
        "occClosingFee": "4.1999958",
        "occFundingFee": "0",
        "cumRealisedPnl": "1.76750995",
        "freeQty": "28",
        "unrealisedPnl": "8.5668",
        "positionIdx": "2",
        "createdTime": "1651594009009",
        "updatedTime": "1652223355185"
      }
    ]
  }
}
```

t(:copy_trade_positon_list)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=pList>/derivatives/v3/copytrading/position/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |false |string |t(:row_comment_symbol)    |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|data |object[] ||
|t(:row_parameter_symbol)|string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|size |string |t(:row_comment_position_size)  |
|position_value |string |t(:row_comment_position_value)  |
|entry_price |string |t(:row_comment_entry_price)  |
|liq_price |string |t(:row_comment_liq_price)  |
|bust_price |string |t(:row_comment_bust_price)  |
|markPrice |string |t(:row_comment_resp_mark_price)  |
|leverage |string |t(:resp_field_leverage)  |
|is_isolated | string | t(:row_comment_isolated) |
|position_margin |string |t(:row_comment_position_margin)  |
|occ_closing_fee |string |t(:row_comment_occ_closing_fee)  |
|occ_funding_fee |string |t(:row_comment_occ_funding_fee)  |
|cum_realised_pnl |string |t(:row_comment_cum_realised_pnl)  |
|freeQty |string |t(:linear_resp_field_free_qty)  |
|unrealised_pnl |string |t(:row_comment_unrealised_pnl)  |
|position_idx |string |t(:copy_trade_row_comment_position_idx)  |
|created_at |int64 |t(:row_comment_created_at_position)  |
|updated_at |int64 |t(:row_comment_updated_at)  |


### t(:copy_trade_positon_close)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/derivatives/v3/copytrading/position/close \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSD",margin:"10","timestamp":{timestamp},"sign":"{sign}"}'
```

```python--old
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Positions.Positions_changeMargin(symbol="BTCUSD", margin="10").result())
```

```python--pybit
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com",
               api_key="", api_secret="")
print(session.change_margin(
    symbol="BTCUSD",
    margin=0.00001
))
```

> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "success",
    "result": {}
}
```

t(:copy_trade_positon_close)

<aside class="notice">
t(:account_aside_changeMargin)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=pChangePositionMarginNew>/derivatives/v3/copytrading/position/close</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pChangePositionMarginNew"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)    |
|position_idx |<b>true</b>|string |t(:copy_trade_row_comment_position_idx)  |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |



### t(:copy_trade_set_leverage)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/derivatives/v3/copytrading/position/leverage-set \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSDT","buyLeverage":"14","sellLeverage":"14",timestamp":{timestamp},"sign":"{sign}"}'
```

```python--old
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Positions.Positions_saveLeverage(symbol="BTCUSDT", buyLeverage="14",sellLeverage="14").result())
```

```python--pybit
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com",
               api_key="", api_secret="")
print(session.set_leverage(
    symbol="BTCUSD",
    buyLeverage="14",
    sellLeverage="14"))
```

> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "success",
    "result": {}
}
```

t(:copy_trade_set_leverage)

<aside class="notice">
t(:account_aside_setleverage)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=ulSaveNew>/derivatives/v3/copytrading/position/leverage-set</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#ulSaveNew"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol |<b>true</b> |string |t(:row_comment_symbol)    |
|buyLeverage |<b>true</b> |string |t(:copy_trade_comment_leverage) |
|sellLeverage |<b>true</b> |string |t(:copy_trade_comment_leverage) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |




## t(:risklimit)
### t(:getrisklimit)
> t(:codequote_curlExample)

```console
curl "https://api-testnet.bybit.com/v2/public/risk-limit/list?symbol=BTCUSD"
```

```python--old
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Wallet.Wallet_getRiskLimit().result())
```

```python--pybit
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com")
print(session.get_risk_limit(
    symbol="BTCUSD"
))
```


> t(:codequote_responseExample)

```javascript
{
    "ret_code":0,
    "ret_msg":"OK",
    "ext_code":"",
    "ext_info":"",
    "result":[
        {
            "id":1,
            "symbol":"BTCUSD",
            "limit":1000000,
            "maintain_margin":0.005,
            "starting_margin":0.01,
            "section":[
                "1",
                "2",
                "3",
                "5",
                "10",
                "25",
                "50",
                "100"
            ],
            "is_lowest_risk":1,
            "created_at":"2021-03-17T08:20:53.000Z",
            "updated_at":"2021-03-17T08:20:53.000Z",
            "max_leverage":100
        },
        ...
        {
            "id":10,
            "symbol":"BTCUSD",
            "limit":10000000,
            "maintain_margin":0.05,
            "starting_margin":0.055,
            "section":[
                "1",
                "2",
                "3",
                "4",
                "5",
                "10",
                "15",
                "18"
            ],
            "is_lowest_risk":0,
            "created_at":"2021-03-17T08:21:12.000Z",
            "updated_at":"2021-03-17T08:21:12.000Z",
            "max_leverage":18.18
        }
    ],
    "time_now":"1616052270.701108"
}
```

t(:account_para_getRisk)

<aside class="notice">
t(:account_aside_getRisk_inverse)
</aside>

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=oawrlList>/v2/public/risk-limit/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oawrlList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>false</b> |string |t(:row_comment_symbol) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|id |number |t(:row_comment_riskId)  |
|t(:row_parameter_symbol) |string |t(:row_comment_symbol)  |
|limit |number |t(:row_comment_risk_limit)    |
|maintain_margin |number |t(:row_comment_maintain_margin)  |
|starting_margin |number |t(:row_comment_starting_margin_inverse)  |
|section |string |t(:row_comment_section)  |
|is_lowest_risk |number |t(:row_comment_is_lowest_risk)    |
|created_at |string |t(:row_comment_created_at)  |
|updated_at |string |t(:row_comment_updated_at)  |
|max_leverage |string |t(:row_comment_max_leverage)  |


### t(:setrisklimit)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/v2/private/position/risk-limit \
-H "Content-Type: application/json" \
-d '{"api_key":"{api_key}","symbol":"BTCUSD","risk_id":2,"timestamp":{timestamp},"sign":"{sign}"}'
```

```python--pybit
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com",
               api_key="", api_secret="")
print(session.set_risk_limit(
    symbol="BTCUSD",
    risk_id=2
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "OK",
    "ext_code": "",
    "ext_info": "",
    "result": {
        "risk_id": 2
    },
    "time_now": "1620283810.393787",
    "token": null
}
```

<aside class="notice">
t(:account_aside_getRisk_inverse)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=oawrlList>/v2/private/position/risk-limit</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oawrlList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|risk_id |<b>true</b> |integer |t(:row_comment_riskId) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|risk_id |number |t(:row_comment_riskId)  |


## t(:funding)
### t(:fundingRate)
> t(:codequote_curlExample)

```console
curl "https://api-testnet.bybit.com/v2/public/funding/prev-funding-rate?symbol=BTCUSD"
```

```python--old
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Funding.Funding_prevRate(symbol="BTCUSD").result())
```

```python--pybit
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com")
print(session.get_the_last_funding_rate(
    symbol="BTCUSD"
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "ok",
    "ext_code": "",
    "result": {
        "symbol": "BTCUSD",
        "funding_rate": "0.00010000",
        "funding_rate_timestamp": 1577433600
    },
    "ext_info": null,
    "time_now": "1577445586.446797",
    "rate_limit_status": 119,
    "rate_limit_reset_ms": 1577445586454,
    "rate_limit": 120
}
```

<aside class="notice">
t(:fundingRate_notice)
</aside>

t(:market_para_fundingRate)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=oafPrevFundingRateNew>/v2/public/funding/prev-funding-rate</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oafPrevFundingRateNew"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|parameter|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)    |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|t(:row_parameter_symbol) |string |t(:row_comment_symbol)    |
|funding_rate |string |t(:row_comment_funding_rate)  |
|funding_rate_timestamp |number |t(:row_comment_funding_rate_timestamp)  |

### t(:mylastfundingfee)
> t(:codequote_curlExample)

```console
curl "https://api-testnet.bybit.com/v2/private/funding/prev-funding?api_key={api_key}&symbol=BTCUSD&timestamp={timestamp}&sign={sign}"
```

```python--old
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Funding.Funding_myLastFee(symbol="BTCUSD").result())
```

```python--pybit
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com")
print(session.get_the_last_funding_rate(
    symbol="BTCUSD"
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "ok",
    "ext_code": "",
    "result": {
        "symbol": "BTCUSD",
        "side": "Buy",  // Your position side at the time of settlement
        "size": 1,      // Your position size at the time of settlement
        "funding_rate": 0.0001,  // Funding rate for settlement. When the funding rate is positive, longs pay shorts. When it is negative, shorts pay longs.
        "exec_fee": 0.00000002,  // Funding fee.
        "exec_timestamp": 1575907200  // The time of funding settlement occurred, UTC timestamp
    },
    "ext_info": null,
    "time_now": "1577446900.717204",
    "rate_limit_status": 119,
    "rate_limit_reset_ms": 1577446900724,
    "rate_limit": 120
}
```

t(:account_para_myLastFunding)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=oafPrevFundingNew>/v2/private/funding/prev-funding</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oafPrevFundingNew"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)    |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|t(:row_parameter_symbol) |string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |string |t(:row_comment_funding_side)  |
|size |number |t(:row_comment_funding_position_size)  |
|funding_rate |number |t(:row_comment_funding_rate)  |
|exec_fee |number |t(:row_comment_exec_fee)  |
|exec_timestamp |number |t(:row_comment_exec_timestamp)  |


### t(:predictedfunding)
> t(:codequote_curlExample)

```console
curl "https://api-testnet.bybit.com/v2/private/funding/predicted-funding?api_key={api_key}&symbol=BTCUSD&timestamp={timestamp}&sign={sign}"
```

```python--old
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Funding.Funding_predicted(symbol="BTCUSD").result())
```

```python--pybit
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com",
               api_key="", api_secret="")
print(session.predicted_funding_rate(
    symbol="BTCUSD"
))
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "ok",
    "ext_code": "",
    "result": {
        "predicted_funding_rate": 0.0001,
        "predicted_funding_fee": 0
    },
    "ext_info": null,
    "time_now": "1577447415.583259",
    "rate_limit_status": 118,
    "rate_limit_reset_ms": 1577447415590,
    "rate_limit": 120
}
```
t(:account_para_predictedFunding)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=oafPredictedFundingNew>/v2/private/funding/predicted-funding</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oafPredictedFundingNew"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)    |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|predicted_funding_rate |number |t(:row_comment_predicted_funding_rate)    |
|predicted_funding_fee |number |t(:row_comment_predicted_funding_fee)  |

## t(:key)
> t(:codequote_curlExample)

```console
curl "https://api-testnet.bybit.com/v2/private/account/api-key?api_key={api_key}&timestamp={timestamp}&sign={sign}"
```

```python--old
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.APIkey.APIkey_info().result())
```

```python--pybit
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com",
               api_key="", api_secret="")
print(session.api_key_info())
```

> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "ok",
    "ext_code": "",
    "result": [
        {
            "api_key": "7GkMBBLTbGRfa0Nuh1",
            "type": "personal",
            "user_id": 1,
            "inviter_id": 3,
            "ips": [
                "*"
            ],
            "note": "scalping_bot",
            "permissions": [
                "Order",
                "Position"
            ],
            "created_at": "2019-10-28T13:22:39.000Z",
            "expired_at": "2020-01-28T13:22:39.000Z",
            "read_only": false,
            "vip_level":"",
            "mkt_maker_level":""
        }
    ],
    "ext_info": null,
    "time_now": "1577445138.790150",
    "rate_limit_status": 99,
    "rate_limit_reset_ms": 1577445138812,
    "rate_limit": 100
}
```

t(:account_para_key)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=oaApiKeyNew>/v2/private/account/api-key</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oaApiKeyNew"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|api_key |string |t(:row_comment_api_key)    |
|type |string |t(:row_comment_type)  |
|user_id |number |t(:row_comment_position_user_id)  |
|inviter_id |number |t(:row_comment_position_inviter_id)  |
|ips |string |t(:row_comment_position_ips)  |
|note |string |t(:row_comment_note)  |
|permissions |string |t(:row_comment_permissions)  |
|created_at |string |t(:row_comment_created_at)  |
|expired_at |string |t(:row_comment_expired_at)  |
|read_only |bool |t(:row_comment_read_only)  |
|vip_level |string |t(:row_comment_vip_level)  |
|mkt_maker_level |string |t(:row_comment_mkt_maker_level)  |

## t(:lcp)
> t(:codequote_curlExample)

```console
curl "https://api-testnet.bybit.com/v2/private/account/lcp?api_key={api_key}&symbol=BTCUSD&timestamp={timestamp}&sign={sign}"
```

```python--pybit
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com",
               api_key="", api_secret="")
print(session.lcp_info(
    symbol="BTCUSD"
))
```


> t(:codequote_responseExample)

```javascript
{
    "ret_code": 0,
    "ret_msg": "ok",
    "ext_code": "",
    "result": [
        "lcp_list": [
        {
            "date": "2020-04-27",
            "self_ratio": 0,
            "platform_ratio": 0,
            "score": 0.1459
        },
        {
            "date": "2020-04-26",
            "self_ratio": 0,
            "platform_ratio": 0,
            "score": 0.1459
        }
        ]
    ],
    "ext_info": null,
    "time_now": "1577445138.790150",
    "rate_limit_status": 99,
    "rate_limit_reset_ms": 1577445138812,
    "rate_limit": 100
}
```

t(:account_para_lcp)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=oaApiLcp>/v2/private/account/lcp</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oaApiLcp"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)    |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|date |string |t(:row_comment_lcp_date)    |
|self_ratio |number |t(:row_comment_lcp_self_ratio)  |
|platform_ratio |number |t(:row_comment_lcp_platform_ratio)  |
|score |number |t(:row_comment_lcp_score)  |
