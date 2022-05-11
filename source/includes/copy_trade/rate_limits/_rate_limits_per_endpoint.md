### t(:understandingratelimits)
t(:rate_para_understanding)

```
"rate_limit_status": 119,
"rate_limit_reset_ms": 1572114055663,
"rate_limit": 120
```

* `rate_limit_status` - t(:rate_text_limitStatus_understanding)
* `rate_limit` - t(:rate_text_limit_understanding)
* `rate_limit_reset_ms` - t(:rate_text_limitReset)

### t(:perendpoint)
<table class="custom_table">
  <tr>
    <th>t(:row_comment_rate_limit)</th>
    <th>t(:row_comment_path)</th>
    <th>t(:row_comment_consume)</th>
  </tr>
  <tr>
    <td rowspan="4">75/min</td>  
  </tr>
  <tr><td>/derivatives/v3/copytrading/position/leverage-set </td><td>1 / request</td></tr>
  <tr><td>/derivatives/v3/copytrading/position/close  </td><td>1 / request</td></tr>
  <tr><td>/derivatives/v3/copytrading/position/list  </td><td>1 / request</td></tr>
<tr>
    <td rowspan="5">100/min</td>  
  </tr>
 <tr><td>/derivatives/v3/copytrading/order/create </td><td>1 / request</td></tr>
  <tr><td>/derivatives/v3/copytrading/order/close </td><td>1 / request</td></tr>
  <tr><td>/derivatives/v3/copytrading/order/cancel  </td><td>1 / request</td></tr>
  <tr><td>/derivatives/v3/copytrading/order/list  </td><td>1 / request</td></tr>

  <tr>
    <td rowspan="3">120/min</td>
  </tr>
  <tr><td>/derivatives/v3/copytrading/wallet/balance</td><td>1 / request</td></tr>
  <tr><td>/derivatives/v3/copytrading/wallet/transfer</td><td>1 / request</td></tr>
</table>
