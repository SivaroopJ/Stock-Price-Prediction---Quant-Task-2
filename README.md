# Stock-Price-Prediction---Quant-Task-2

  
			Why Britannia?
Britannia Industries Limited is an Indian multinational food products company, which sells biscuits, breads and dairy products. Its brand recognition and customer loyalty could contribute to stable revenue streams. Britannia offers a wide range of products. A diversified company can help mitigate risks associated with fluctuation in the market. Britannia is one of the leading players in the Fast-Moving Consumer Goods sector. As one of the Nifty50 companies, the volume of trade is higher compared to others. We also have a large amount of historical data about its market performances. 

			Selection of Timeframe

The timeframe selected is from 1st January 2019 to 31st December 2023. This provides the latest historical data about the selected stock and thus gives better model for predicting near future market.


LABELING
First of all i made a bubble around the stock price as a way to prevent false signals to trigger my other labeling conditions. I chose an upper threshold of SD/3 of the logarithmic daily return of the stock. The lower bound was SD/6 of the same. The label would be to sell if the closing price went below the lower bound of the previous day or if the closing price went above the upper bound of the previous day and became a maxima. 

The label would be buy if the stock reached a minima. 

The label is Hold in all other cases.

 
I inferred Hold as sticking to your current outlook on the market(Buy/Sell).

INDICATORS

MACD
The MACD indicator serves several essential functions in technical analysis. Firstly, it aids in trend identification by discerning the direction of price movements. When the MACD line resides above the signal line, it suggests a bullish trend, while a MACD line below the signal line indicates a bearish trend. This feature enables traders to align their strategies with prevailing market trends effectively.
Moreover, MACD facilitates momentum measurement, allowing traders to assess the strength of price movements. Rapid shifts in the MACD histogram signify changes in momentum, enabling traders to anticipate potential trend reversals. By closely monitoring MACD movements, traders can make informed decisions regarding entry and exit points in the market.


RSI
The Relative Strength Index (RSI) is a momentum oscillator that measures the speed and change of price movements. RSI is calculated using the average gain and average loss over a specified period, typically 14 periods. RSI values range from 0 to 100, with readings above 70 considered overbought and readings below 30 considered oversold.


ADX
ADX serves several essential functions in technical analysis. Firstly, it helps traders assess the strength of trends in the market. When ADX readings surpass the 25 threshold, it suggests that the market is trending strongly, whether it's an uptrend or a downtrend. Conversely, ADX readings below 20 indicate a lack of strong directional movement, signalling a potential consolidation phase or range-bound market. Moreover, ADX facilitates trend confirmation by distinguishing between trending and non-trending market conditions.


Bollinger Bands
Bollinger Bands serve several key functions in technical analysis. Firstly, they provide a visual representation of price volatility. During periods of high volatility, the bands widen, indicating increased price fluctuations, while narrow bands suggest lower volatility and potential upcoming price movements.
Moreover, Bollinger Bands help traders identify potential trend reversals and overbought/oversold conditions. When prices touch or penetrate the upper band, it may signal an overbought condition, potentially indicating a reversal to the downside. Conversely, when prices touch or penetrate the lower band, it may suggest an oversold condition and a potential reversal to the upside.

I passed the difference between the closing price and upper bound, the closing price and lower bound as two features.

OBV
OBV serves several essential functions in technical analysis. Firstly, it helps traders confirm price trends by analyzing volume trends alongside price movements. When OBV trends in the same direction as the price, it confirms the strength of the trend. For example, rising prices accompanied by increasing OBV indicate bullish momentum, while falling prices with decreasing OBV suggest bearish momentum. Divergences between OBV and price movements can also provide early warning signs of potential trend reversals.


EMA-9-21
The combination of EMA 9 and EMA 21 serves several key functions in technical analysis. Firstly, it helps traders identify short-term and medium-term trends in the market. When EMA 9 crosses above EMA 21, it signals a potential bullish trend reversal or continuation, whereas a crossover below suggests a potential bearish trend reversal or continuation. These crossovers provide actionable insights for traders to enter or exit positions based on trend changes.
Moreover, EMA 9 and EMA 21 act as dynamic support and resistance levels, guiding traders in setting stop-loss orders and determining price targets. 

Modded Resistance 1 and 2
This is basically the difference between the resistance 1 and resistance 2 respectively with closing price. 
R1 and R2 serve several key functions in technical analysis. Firstly, it acts as a significant psychological and technical barrier for traders and investors. When prices approach R1 or R2, traders who bought at lower levels may decide to sell their positions to take profits, leading to increased selling pressure and potential price reversals. Moreover, R1 or R2 provide valuable insights into market sentiment and the strength of bullish trends.
R2 represents a stronger resistance level, and traders may adopt more cautious strategies, such as tightening stop-loss orders or waiting for confirmation of a breakout before entering new positions.

Modded Support 1 and 2
S1 and S2 serve several pivotal functions in technical analysis. Firstly, it acts as a significant psychological and technical barrier for traders and investors. When prices approach S1 or S2, traders who missed out on buying at lower levels may seize the opportunity to enter long positions, contributing to increased buying pressure and potential price reversals.
S2 typically indicates a stronger support level beyond S1, requiring more substantial buying interest to hold. Traders use these levels to identify potential price reversal points and adjust their trading strategies accordingly based on market dynamics and sentiment.


Why these Indicators?


The MACD will help to discern the trend to the model. The ADX compliments this by providing the strength of the strength. The EMA-9-21 also helps it to discern when the trend start to occur. OBV provides a relation between the price and the volume, an important component in every trade. RSI provides the speed in which the price changes. These indicators provide an overall functioning framework to the model.
The Modded Resistances and Supports provides a barrier or covering to the trend, letting us know when a trend starts to breakdown.


CONSTRUCTED FEATURES
Feature_1
This is a rolling mean of the logarithmic daily return of the stock in a window of 4 days.

Feature_2
This is a rolling mean of the difference between the Open and Close prices in a window of 4 days.

Feature_1 and Feature_2 are used to fine tune the position in which the model would buy or sell.
Indicators usually respond to the market only after sometime. I thought adding these features would help me to identify the start and end of a trend more finely.

RESULT

Test Accuracy	: 63.22314049586777
F1 Score	     : 53.57385033013921
ROC		     : 62.876920967970406