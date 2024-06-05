### Hummingbot - Market Making

### Install with Docker


```
git clone https://github.com/hummingbot/hummingbot
cd hummingbot
docker compose up -d
docker attach hummingbot
```
### Connecting the bot with Exchanges
- Run connect [exchange_name] command e.g. connect binance .
- Enter API and secret keys when prompted
- Other exchanges may require additional details such as account ID, exchange address, etc.

### Creating script config files
- To create a configuration file for a compatible, run the create command and add the --script-config flag.
- Add the necessary inputs based on the questions asked in the prompt like the leverage, spread, refresh time etc.,
- In the auto-complete dropdown, only the configurable scripts located in the /scripts folder will be shown.

### Running Live
- Then type start to make the bot run trades in the exchanges.
- To know the status of the bot type status which lists the open orders.
- To know the details like the balance and the volume traded use history command.
- To stop the bot from placing orders, use stop command.
- To make the bot to exit, type exit command.

## Perpetual Market Making Strategy Config

```yaml
template_version: 6
strategy: perpetual_market_making

derivative: binance_perpetual
market: ETH-USDT
leverage: 2
position_mode: Hedge

bid_spread: 0.005
ask_spread: 0.005
minimum_spread: -100.0

order_refresh_time: 60.0
order_refresh_tolerance_pct: 0.01
order_amount: 0.04

long_profit_taking_spread: 0.005
short_profit_taking_spread: 0.005
stop_loss_spread: 0.01
time_between_stop_loss_orders: 60.0
stop_loss_slippage_buffer: 0.01

price_ceiling: -1.0
price_floor: -1.0

order_levels: 1
order_level_amount: 0
order_level_spread: 1.0

filled_order_delay: 60
order_optimization_enabled: false
ask_order_optimization_depth: 0
bid_order_optimization_depth: 0

price_source: current_market
price_type: mid_price

price_source_derivative:
price_source_market:
price_source_custom_api:
custom_api_update_interval: 5.0

order_override:

```
### Additional Commands:
https://hummingbot.org/client/commands-shortcuts/





