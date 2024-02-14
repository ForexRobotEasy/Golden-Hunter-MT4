# Golden Hunter MT4

Golden Hunter MT4 is a custom indicator designed to identify optimal trading pairs in the forex market based on spread and volatility conditions. This indicator is developed by the Forex Robot Easy Team and can be found on their website [forexroboteasy.com](https://forexroboteasy.com).

## Indicator Parameters

The indicator has two input parameters:

1. SpreadLimit: This parameter sets the maximum allowable spread for a trading pair. The default value is set to 2.0.
2. VolatilityLimit: This parameter sets the minimum required volatility for a trading pair. The default value is set to 1.5.

## Indicator Initialization

The indicator initialization function `OnInit()` is responsible for setting up the indicator. In this function, indicator buffers are added for visualization using the `SetIndexBuffer()` function. The indicator name is set using the `IndicatorSetString()` function.

## Indicator Deinitialization

The indicator deinitialization function `OnDeinit()` is responsible for removing indicator buffers. In this function, the `ArrayResize()` function is used to resize the indicator buffers to zero.

## Indicator Calculation

The indicator calculation function `OnCalculate()` is responsible for calculating the spread and volatility values for each bar. In this function, the spread is calculated as the difference between the ask and bid prices, and the volatility is calculated as the difference between the high and low prices. The calculated values are stored in the `SpreadBuffer` and `VolatilityBuffer` arrays.

The function also checks for optimal trading pairs by iterating through the bars in reverse order. If the spread is less than or equal to the `SpreadLimit` and the volatility is greater than or equal to the `VolatilityLimit`, and the trading pair is one of the specified symbols ('EURUSD', 'GBPUSD', 'BTCUSD'), a trading recommendation is generated.

## Expert Advisor Start Function

The expert advisor start function `OnTick()` is responsible for initiating the trading process. It checks if it's daylight hours (between 8 AM and 4 PM), a weekday, and if trading is allowed and the market is not range-bound. If these conditions are met, it selects each symbol and calculates the indicator values using the `IndicatorCalculate()` function. If there is enough data available, it calls the `OnCalculate()` function to generate a trading recommendation.

## Additional Functions

- `IsRangeBoundMarket()`: This function checks if the market is range-bound. The logic for range detection needs to be added by the user.
- `IsTradeAllowed()`: This function checks if trading is allowed. The logic for determining if trading is allowed needs to be added by the user.

## Indicator Buffers

The indicator uses two indicator buffers:

1. `SpreadBuffer`: This buffer stores the calculated spread values for each bar.
2. `VolatilityBuffer`: This buffer stores the calculated volatility values for each bar.

---

This code is a sample implementation of the Golden Hunter MT4 indicator developed by the Forex Robot Easy Team. ForexRobotEasy is not the official developer of this product. To find the official developer and for detailed reviews and trading results of this product, please visit [Golden Hunter MT4 Review](https://forexroboteasy.com/forex-robot-review/golden-hunter-mt4-review-powerful-forex-trading-tool/). For more information about this indicator and its usage, please refer to the official documentation provided by the developer.
