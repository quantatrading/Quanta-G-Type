# Quanta G-Type

Quanta G-Type is a 100% quant-based geometric market maker hybrid designed for long-term trading, capable of handling very large market price movements (100 to 1000x moves). Unlike technical analysis algorithms, this quantitative algorithm is always active and performs across three market states:

- **Sideways Market**: Engages in spread trading by buying and selling at intervals within a stable price range.
- **Price Pump**: Focuses on managed decumulation of the investments' accumulation of assets.
- **Price Dump**: Focuses on managed accumulation of the traded asset.

Quanta G-Type simplifies investment in digital currency markets by managing the emotional aspects of trading, such as when to take profits, how to compound, and how to accumulate.

## Algorithm Purpose

Quanta G-Type is ideal for long-term investors who can handle market volatility and have a long-term investment horizon. It's designed for traders who prefer a "set and forget" approach, focusing on long-term returns rather than quick trades across 100 to 1000x price movement. This strategy can be aggressive but requires significant starting capital, so it's not for the faint-hearted. You can use the [starting calculator](https://docs.google.com/spreadsheets/d/1ycVTNctPpkJSgVM7KMMf1oXkzK8K_YecxJpdfH78lZM) to understand the required capital and potential outcomes.

## How Are Profits Generated?

Profits are generated through four mechanisms, which are fully quantitatively calculated and updated on each tick. These mechanisms ensure that as price moves down, accumulation takes place:

- **Accumulation**: Accumulates the quote (e.g. "BTC") currency by posting orders with the same base (e.g. "USDT") amount. Profits are realised in quote.
- **Decumulation**: Realises profit in the base asset by utilising the accumulated quote at a higher price. Orders are posted with the same quote size. Decumulation is not selling all, it is the financial process of drawing down profit from your investment.
- **Rebalance**: Uses distinct buy and sell order values when deep price moves create an imbalance in buying or selling power.

## What Are My Risks?

Given the long trading horizon, it's important to choose a coin you believe will maintain value over the long term, this requires your knowledge and trading risk. The main risk is price falling below lower bounds, but this is mitigated by trading large ranges. Spread trading gains can offset decreased inventory value during downtrends.

**Remember**: During long declines, market making reduces losses rather than realising actual profits.

## Operational Features

- **Auto Compounding**: Profits are automatically managed to accumulate and compound profits in quote and base.
- **Auto Inventory Management**: Flips profits in either quote or base currency.
- **Auto Trading Limits**: Refreshes balances and order arrays on each buy or sell.
- **Auto Sloping of Buy and Sell Orders**: Orders placed around the price midpoint with profits increasing from the middle to bounds.
- **Performance Indicators**: Detailed metrics including HODL vs. trade comparison, uPNL breakdown, and projected annualized wallet growth.
- **Light API Usage**: Suitable for VPS with multiple instances.
- **Operational Depth Control**: Ensures you catch large volatile moves.
- **Trading Modes**: Accumulation, Decumulation, Rebalance, and Auto modes tailored to market conditions.

## Starting The Strategy - 4 Steps

1. **Determine Trading Bounds**: Use TradingView charts to identify areas of significant support and resistance levels using a weekly or monthly timeframe.
2. **Use the Starting Calculator**: Calculate the triangle of capital, intervals, and range. You can use the calculator to provide different scenarios based on your risk appetite.
3. **Prepare Capital**: Your exchange account must have only BASE (e.g., "USDT"). Quanta G-Type will use your entire base balance and will not run if other pairs are also trading the same base.
4. **Auto Setup**: Ensure Auto Setup is enabled, add your Intervals %, Upper and Lower Bound, Order Depth, and Min Volume to Sell. Do not change any other settings.

![Example of Trading Settings Auto Setup](https://github.com/quantatrading/Quanta-G-Type/assets/3750100/46a3bc05-2413-4af1-be0e-1c4770f9e873)
**Example of the only settings required for an Automatic Setup**

## Additional Important Info

Quanta G-Type uses your entire wallet balance for trading the configured pair. It’s highly advisable to use a distinct sub-account on your exchange.

- **Cancel Orders**: Must be disabled in the global bot settings.
- **Exchange Delay**: A fast exchange delay is not necessary.
- **State File**: Ensure no state files for the pair exist in `/json` or `/json/backup`. Once Quanta G-Type is running, the state file is your database; ensure good practice in backing it up and not deleting it.
- **Adding Capital**: Additional BASE can be added anytime, but you must update the starting balance and starting base balance in Trading Settings > Advanced. The strategy will adapt but may skew performance indicators temporarily.

To start without placing orders, configure `BUY_ENABLED`, `SELL_ENABLED`, and/or `WATCH_MODE` accordingly.
