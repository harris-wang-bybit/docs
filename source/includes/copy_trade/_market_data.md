# t(:marketdata)
t(:market_para_auth)

### t(:copy_trade_symbol_list)
> t(:codequote_curlExample)

```console
curl https://api-testnet.bybit.com/derivatives/v3/copytrading/symbol/list
```

```python--old
import bybit
client = bybit.bybit(test=True, api_key="api_key", api_secret="api_secret")
print(client.Symbol.Symbol_list().result())
```

```python--pybit
from pybit import HTTP
session = HTTP("https://api-testnet.bybit.com")
print(session.symbol_list())
```


> t(:codequote_responseExample)

```javascript
{
  "retCode": 0,
    "retMsg": "success",
    "result": {
    "data": [
      {
        "symbol": "BTCUSDT",
        "baseCurrency": "BTC",
        "quoteCurrency": "USDT",
        "priceScale": "1",
        "takerFee": "0.00075",
        "makerFee": "-0.00025",
        "fundingInterval": "480",
        "leverageFilter": {
          "maxLeverage": "100",
          "minLeverage": "1"
        },
        "priceFilter": {
          "minPrice": "0.5",
          "maxPrice": "999999.0",
          "tickSize": "0.5"
        },
        "lotSizeFilter": {
          "qtyStep": "0.001",
          "maxOrderQty": "100.000",
          "minOrderQty": "0.001"
        }
      },
      {
        "symbol": "ETHUSDT",
        "baseCurrency": "ETH",
        "quoteCurrency": "USDT",
        "priceScale": "2",
        "takerFee": "0.00075",
        "makerFee": "-0.00025",
        "fundingInterval": "480",
        "leverageFilter": {
          "maxLeverage": "50",
          "minLeverage": "1"
        },
        "priceFilter": {
          "minPrice": "0.05",
          "maxPrice": "99999.90",
          "tickSize": "0.05"
        },
        "lotSizeFilter": {
          "qtyStep": "0.01",
          "maxOrderQty": "1000.00",
          "minOrderQty": "0.01"
        }
      },
      {
        "symbol": "EOSUSDT",
        "baseCurrency": "EOS",
        "quoteCurrency": "USDT",
        "priceScale": "3",
        "takerFee": "0.00075",
        "makerFee": "-0.00025",
        "fundingInterval": "480",
        "leverageFilter": {
          "maxLeverage": "50",
          "minLeverage": "1"
        },
        "priceFilter": {
          "minPrice": "0.001",
          "maxPrice": "1999.998",
          "tickSize": "0.001"
        },
        "lotSizeFilter": {
          "qtyStep": "0.1",
          "maxOrderQty": "50000.0",
          "minOrderQty": "0.1"
        }
      },
      {
        "symbol": "XRPUSDT",
        "baseCurrency": "XRP",
        "quoteCurrency": "USDT",
        "priceScale": "4",
        "takerFee": "0.00075",
        "makerFee": "-0.00025",
        "fundingInterval": "480",
        "leverageFilter": {
          "maxLeverage": "50",
          "minLeverage": "1"
        },
        "priceFilter": {
          "minPrice": "0.0001",
          "maxPrice": "199.9998",
          "tickSize": "0.0001"
        },
        "lotSizeFilter": {
          "qtyStep": "1",
          "maxOrderQty": "1000000",
          "minOrderQty": "1"
        }
      },
      {
        "symbol": "DOGEUSDT",
        "baseCurrency": "DOGE",
        "quoteCurrency": "USDT",
        "priceScale": "4",
        "takerFee": "0.00075",
        "makerFee": "-0.00025",
        "fundingInterval": "480",
        "leverageFilter": {
          "maxLeverage": "25",
          "minLeverage": "1"
        },
        "priceFilter": {
          "minPrice": "0.0001",
          "maxPrice": "199.9998",
          "tickSize": "0.0001"
        },
        "lotSizeFilter": {
          "qtyStep": "1",
          "maxOrderQty": "200000",
          "minOrderQty": "1"
        }
      }
    ]
  }
}
```

t(:copy_trade_symbol_list)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpSymbols>/derivatives/v3/copytrading/symbol/list</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpSymbols"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|parameter|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|symbol |string |t(:row_response_comment_name)    |
|baseCurrency |string |t(:row_response_comment_base_currency)    |
|quoteCurrency |string |t(:row_response_comment_quote_currency)    |
|priceScale |string |t(:row_response_comment_price_scale)    |
|takerFee |string |t(:row_response_comment_taker_fee)    |
|makerFee |string |t(:row_response_comment_maker_fee)    |
|fundingInterval |string |t(:row_response_funding_interval)    |
|leverageFilter |object[] ||
|min_leverage |number |t(:row_response_comment_min_leverage)    |
|max_leverage |number |t(:row_response_comment_public_max_leverage)    |
|priceFilter |object[] ||
|minPrice |string |t(:row_response_comment_min_price)    |
|maxPrice |string |t(:row_response_comment_max_price)    |
|lotSizeFilter |object[] ||
|maxOrderQty |number |t(:row_response_comment_max_trading_qty)    |
|minOrderQty |number |t(:row_response_comment_min_trading_qty)    |
|qtyStep |number |t(:row_response_comment_qty_step)    |



