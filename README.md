# Trading_Strategies

![image](https://user-images.githubusercontent.com/53173112/237058091-9c0b02e6-d64a-4e7f-8336-b649b6090952.png)

# MACD with rebalancing between different sectors each year
My irst strategy was to use Moving Average Convergence Divergence (MACD) and rebalance my investing according to the success in the previous year for the next year.
The MACD indicator is calculated using the MACD function, and the resulting MACD and signal lines are added as new columns to the input dataframe df. The macd_position column is created to track whether to buy or sell based on MACD, and the macd_signal column is created to track the change in position. The function then loops through each row of the dataframe and generates buy and sell signals based on the MACD strategy. When the MACD line crosses above the signal line, the function buys the stock by calculating the number of shares to buy based on the available balance. Similarly, when the MACD line crosses below the signal line, the function sells the stock and calculates the new balance based on the number of shares sold. Finally, the function returns the final balance and the number of trades made during the MACD trading strategy.
Rebalance – We created a function which calculates the new investment amounts for each sector based on the total balance and the proportional profit/loss from the previous year. First, the initial investment amount is set to be the same as the total balance ( first year of investment we invest equally 100000$ in each sector) . Then, the function sums up the profit/loss values for each sector from the previous year to get the total profit/loss. Next, the function calculates the proportional profit/loss for each sector by dividing each sector's profit/loss from the previous year by the total profit/loss. This gives a percentage value that represents each sector's contribution to the total profit/loss. Finally, the function calculates the new investment amounts for each sector by multiplying the proportional profit/loss values by the initial investment amount. The result is a dictionary that maps each sector name to its corresponding new investment amount. The function then returns this dictionary of new investment amounts.

# Example:
Let's say we have a total balance of $100,000 and we have invested it in three different sectors:
• Sector A: $30,000
• Sector B: $50,000
• Sector C: $20,000
Now let's assume that at the end of the previous year, each sector had the following profit/loss values:
• Sector A: $10,000 profit
• Sector B: $5,000 loss
• Sector C: $15,000 profit
To calculate the new investment amounts for each sector:
Initial investment amount = $100,000
Total profit/loss = $10,000 - $5,000 + $15,000 = $20,000
Then, we calculate the proportional profit/loss for each sector by dividing each sector's profit/loss from the previous year by the total profit/loss:
• Sector A: $10,000 / $20,000 = 0.5 or 50%
• Sector B: -$5,000 / $20,000 = -0.25 or -25%
• Sector C: $15,000 / $20,000 = 0.75 or 75%
Finally, we calculate the new investment amounts for each sector by multiplying the proportional profit/loss values by the initial investment amount:
• Sector A: 0.5 * $100,000 = $50,000
• Sector B: -0.25 * $100,000 = -$25,000 (loss, so negative value)
• Sector C: 0.75 * $100,000 = $75,000
The result of this function is a dictionary: {'Sector A': $50,000, 'Sector B': -$25,000 mean 0, 'Sector C': $75,000}

# Results of this strategy:
2010-2023:
Balance on the bank account at the end of 13 years: 1,759,974 when
Total Profit: 659,974 (The total profit is calculated as the difference between the final bank account balance and the initial investment of $1,100,000.) The return percentage is calculated as the total profit divided by the initial investment, which is $1,100,00 which is approximately 60%.
Return percent:~0.6
2019-2023:
Balance on the bank account at the end of 4 years and 3 months is :1534973
Total Profit:434973
Return percent: ~0.4
2022-2023:
Balance on the bank account:1146531
Total Profit: 46531
Return percent:~0.04

![image](https://user-images.githubusercontent.com/53173112/237058249-bb6f73fc-4f03-459c-8d98-037664ff7c4b.png)
![image](https://user-images.githubusercontent.com/53173112/237058320-8bc0b3a5-2814-432b-af1f-d9cb7cde6cb2.png)

# Opinion:
Assuming that you invested $100,000 in each of the 11 ETFs listed at the beginning of 2010 and that all dividends were reinvested without using any strategy I would earn more money just investing the equal amount and not changing anything. So, even I have a profit it’s doesn’t mean that it’s a good strategy. More other, this is a gross profit – each trade also has a cost (trading fee), taxes, Inflation during the investment period can also reduce the actual profit earned. Maybe if use MACD with long term investment strategy, and various different factors (for example make changes according to the political map or stability in the market, in my opinion it could improve the results). We look at the profit not in the form of what We earned but what We could have earn. Ultimately, it is important to not solely focus on the profit earned but also consider the potential profit that could have been earned with a better investment strategy.

# TREND Strategy 
The trading strategy buys a stock if its price has gone up for five consecutive days and sells the stock if its price has gone down for two consecutive days after a buy. In the beginning we invest 100,000 to each sector. Results:
2010-2023:
Balance on the bank account at the end of 13 years: 1,195, 182 when
Total Profit: 95,182
Return percent:~0.086
2019-2023:
Balance on the bank account at the end of 4 years and 3 months is : 1,071,093
Total Profit: -28906
Return percent: ~-0.026
2022-2023:
Balance on the bank account: 1,084,920
Total Profit: -15079
Return percent:~ -0.0137
Well, that was not a good strategy, but it provided to us some insights. First maybe we can play with the trend, for example to change the direction, to buy when it goes down for 5 days and sell goes up for 6 days?
2010-2023:
Balance on the bank account at the end of 13 years: 2,300,160 when
Total Profit: 1,200,160
Return percent:~ 1.09
2019-2023:
Balance on the bank account at the end of 4 years and 3 months is : 1,334,104
Total Profit: 234,104
Return percent: ~0.21
2022-2023:
Balance on the bank account: 1,235,846
Total Profit: 135,846
Return percent:~ 0.123
Well, the modified function performs much better. More than that, in my opinion, this strategy is less suitable for stable market, like from 2010 to 2019, but it performs better in the unstable market, where there is a lot of fluctuations of the price in the market. So my advice is to change between strategies according to the stability in the market.

![image](https://user-images.githubusercontent.com/53173112/237058701-9b61767c-b094-404c-83d2-2f99e0ea063c.png)
![image](https://user-images.githubusercontent.com/53173112/237058741-3ed42ff0-cfd5-4873-aeeb-41fcaf288fe5.png)


# BollingerBands strategy

![image](https://user-images.githubusercontent.com/53173112/237058789-8f7e426d-07b8-4fb3-a007-6f1485056a37.png)

Ok, if we were invested from the beginning for this strategy, for example 100,000 USD for each sector, then the results will be:
2010-2023:
Balance on the bank account at the end of 13 years: 3,100,536 when
Total Profit: 2000536
Return percent:~ 1.818
2019-2023:
Balance on the bank account at the end of 4 years and 3 months is : 1,435,098
Total Profit: 335,098
Return percent: ~0.3046
2022-2023:
Balance on the bank account: 1,125,033
Total Profit: 25,033
Return percent:~ 0.022

![image](https://user-images.githubusercontent.com/53173112/237058875-cb9fd9e7-ebfb-4471-b3af-159530b6d36a.png)
![image](https://user-images.githubusercontent.com/53173112/237058896-1fa67d64-12b3-4479-a2f6-c1983faa8ad9.png)

Not such a good strategy, maybe only for 2019-2023, but it is generally better to invest in S&P500 and leave the investment untouched for a minimum of 10 years. So what we can change? Maybe we can invest only in specific sectors which are more profitable.
An alternative approach could be to invest only in specific sectors that have proven to be more profitable. For instance, an investor in 2010 could use the BollingerBands strategy on data from 2009 to 2010 to determine the three most profitable sectors. Then, at the start of 2010, the investor can invest only in those sectors using the BollingerBands strategy. In 2011, the investor can pause and reassess the three most profitable sectors from the data of 2009-2010 and reinvest accordingly. The investment sum
can be allocated based on the profitability of the sectors. For instance, 0.5 of the portfolio can be invested in the most profitable sector, 0.3 in the second most profitable sector, and 0.2 in the third most profitable sector.
2010-2023
Balance on the bank account at the end of 13 years: 2,245,493 when
Total Profit: 1,245, 493
Return percent:~ 1.245
2019-2023:
Balance on the bank account at the end of 4 years and 3 months is : 1,007,383
Total Profit: 7383
Return percent: ~ 0.007
2022-2023:
Balance on the bank account 840,598
Total Profit: -159,401
Return percent:~ -0.16
Well, it looks like for this strategy each year to reinvest is not the best thing, and comparing to the previous results, it’s better to put the founds 1100,000 from the start in different sectors, in each sector 100,000, and we will get better performance without changing my investment.
Another approach to consider is changing the investment strategy on a monthly basis. As an investor, one could assess the performance of the last 12 months and invest only in the top three performing sectors with a weight of 0.5, 0.3, and 0.2 accordingly, each month.
2010-2023:
Balance on the bank account at the end of 13 years: 1,019,011 when
Total Profit: 19,011
Return percent:~ 0.019
2019-2023:
Balance on the bank account at the end of 4 years and 3 months is : 1,020,886
Total Profit: 20,886
Return percent: ~ 0.02
2022-2023:
Balance on the bank account 1,005,381
Total Profit: 5,381
Return percent: ~ 0.005
In my opinion it’s not the best strategy, but we think we could improve it, there is a lot of things can be done, and there is a lot of way to improve this strategy.

# The strategies of buying stocks in September, after the New Year, and on Christmas are examples of seasonal investing strategies ( buying strategy )

The "September Effect" is a theory that suggests that stock prices tend to decline in September. Some investors believe that this is due to investors selling stocks to pay for back-to-school expenses or that institutional investors rebalance their portfolios in September. As a result, buying stocks after September may be seen as a good opportunity to invest. The "January Effect" is another seasonal strategy where investors buy stocks at the start of the year. It's based on the idea that investors sell stocks in December to realize losses for tax purposes and then buy them back in January, leading to a temporary increase in stock prices. Buying stocks around Christmas is also a seasonal strategy. Historically, stock prices tend to rise during the week between Christmas and New Year's Day. Some investors attribute this to optimism about the upcoming year and holiday bonuses being invested in the stock market.
2010-2023:
Balance on the bank account at the end of 13 years: 1,429,570 when
Total Profit: 329,570
Return percent:~ 0.29
2019-2023:
Balance on the bank account at the end of 4 years and 3 months is : 1,126,361
Total Profit: 26,361
Return percent: ~ 0.02
2022-2023:
Balance on the bank account 1,083,474
Total Profit: -16,525
Return percent: ~ -0.015

![image](https://user-images.githubusercontent.com/53173112/237058982-ef263d91-ea01-4b8c-9e9a-5895483387b6.png)
![image](https://user-images.githubusercontent.com/53173112/237059017-87c3c1e7-5736-4684-9eaa-b4356ff92b69.png)


# INFLATION STRATEGY
Based on the sectors in my investment portfolio, here are some general observations on how inflation could impact them:
XLK (Technology): The technology sector is generally less sensitive to inflation since it is driven more by innovation and intellectual property than by physical inputs. However, rising interest rates associated with inflation can negatively impact technology companies, as they rely on borrowing to finance growth.
XLE (Energy): The energy sector is highly sensitive to changes in input costs such as oil and gas prices, which can be influenced by inflation. If inflation leads to higher energy prices, this could boost the earnings of energy companies.
XLF (Financials): Financial companies may be impacted by inflation in various ways. If interest rates rise due to inflation, this could increase the profitability of financial companies such as banks. However, inflation could also increase loan defaults and reduce the value of assets held by financial companies.
XLV (Health Care): Health care is a sector that is generally less impacted by inflation since it is largely driven by demographics and medical innovation. However, rising costs of medical supplies and labor could increase expenses for health care companies.
XLRE (Real Estate): Real estate is a sector that can be both positively and negatively affected by inflation. Higher inflation can lead to higher rents, which can benefit real estate companies that own properties. However, rising interest rates associated with inflation could reduce demand for real estate and increase borrowing costs.
XLB (Materials): The materials sector is highly sensitive to changes in input costs such as raw materials and energy, which can be impacted by inflation. If inflation leads to higher prices for these inputs, it could increase costs for materials companies.
XLY (Consumer Discretionary): The consumer discretionary sector includes companies that sell non-essential goods and services, such as retail, media, and entertainment. This sector is generally more sensitive to inflation than the consumer staples sector, as consumers may cut back on discretionary spending during times of inflation.
XLP (Consumer Staples): The consumer staples sector includes companies that sell essential goods such as food, beverages, and household products. This sector is generally less sensitive to inflation since demand for these products tends to remain relatively stable during economic downturns.
XLU (Utilities): The utilities sector is generally considered a defensive sector, as demand for electricity, gas, and water tends to be relatively stable during economic downturns. However, rising input costs associated with inflation could increase expenses for utilities companies.
XLI (Industrials): The industrials sector is highly sensitive to changes in input costs such as raw materials and energy, which can be impacted by inflation. If inflation leads to higher prices for these inputs, it could increase costs for industrial companies.
IYZ (Telecom): The telecom sector is generally less sensitive to inflation since it is driven more by technology and innovation than by physical inputs. However, rising interest rates associated with inflation can negatively impact telecom companies, as they rely on borrowing to finance growth.
Strategy:
The function inflation_strategy is an implementation of an investment strategy that reallocates investments in different sectors based on changes in the inflation rate. How it works? The function
determines the current inflation rate and sells all shares if the rate has changed since the previous row. So we have 3 option to buy stocks according to inflation rate ( for example if inflation between 0 and 0.02 so we will invest my fonds “balance” like this 1,000,000 * 0.2 in XLK and so on – first option. Then next day, we check the inflation rate again. If inflation rate goes up, for example if inflation now is between 0.02 and 0.04 so we sell all my stock on that day and invest my new balance in option two, and so on.
1. (0, 0.02): {'XLK': 0.2, 'XLE': 0.2, 'XLF': 0.2, 'XLV': 0.1, 'XLRE': 0.1, 'XLB': 0.05, 'XLY': 0.05, 'XLP': 0.05, 'XLU': 0.05, 'XLI': 0.05},
2. (0.02, 0.04): {'XLK': 0.1, 'XLE': 0.3, 'XLF': 0.2, 'XLV': 0.05, 'XLRE': 0.1, 'XLB': 0.05, 'XLY': 0.05, 'XLP': 0.05, 'XLU': 0.05, 'XLI': 0.1},
3. (0.04, np.inf): {'XLK': 0.05, 'XLE': 0.4, 'XLF': 0.15, 'XLV': 0.05, 'XLRE': 0.1, 'XLB': 0.05, 'XLY': 0.05, 'XLP': 0.05, 'XLU': 0.05, 'XLI': 0.1}
4. }
2010-2023:
Balance on the bank account at the end of 13 years 3,834,733 when
Total Profit: 2,734,733
Return percent:~ 2.486
2019-2023:
Balance on the bank account at the end of 4 years and 3 months is : 1,844,775
Total Profit: 744,775
Return percent: ~ 0.677
2022-2023:
Balance on the bank account 1,166,338.18
Total Profit: 66,338
Return percent: ~ 0.06

![image](https://user-images.githubusercontent.com/53173112/237059109-fd4fc919-77dc-48a7-92d9-0056ce809cd4.png)
![image](https://user-images.githubusercontent.com/53173112/237059137-db78b15e-2643-4a0e-8c0e-02f8d85c5e23.png)

# Summary – Best strategy
![image](https://user-images.githubusercontent.com/53173112/237057541-82e2f652-bda3-48fd-91f0-2db2fbc20aa1.png)
![image](https://user-images.githubusercontent.com/53173112/237057572-1d66ae28-f646-4396-ba49-cb0e2f69e323.png)
![image](https://user-images.githubusercontent.com/53173112/237057591-c29ff846-1f28-454f-85af-26c469c30d8d.png)
![image](https://user-images.githubusercontent.com/53173112/237057614-bd7adf1f-397a-4849-8eb8-cb85cf7c8d32.png)

Well I did simple 5 strategies in this paper just to check the rumors :) , and the rank is:
1. INFLATION STRATEGY
The primary reason for the success of this investment strategy is its consistent performance in both stable and volatile market conditions, including the recent pandemic period. Furthermore, this approach has delivered superior returns when compared to other investment strategies. In my opinion, this approach is more closely aligned with the actual state of the market as it relies less on historical data and instead adjusts to current market conditions. For instance, during periods of strong inflation,
we reduce my investments in sectors such as XLY or XLB, which are highly sensitive to inflation. Instead, we shift my focus to more stable and less inflation-sensitive sectors like XLU or XLV, which appear more attractive for investment. On the other hand, during periods of low inflation, we may increase my investments in sectors such as XLK or XLF. In summary, this investment strategy's success can be attributed to its adaptability to current market conditions, which allows us to make informed investment decisions and achieve superior returns.
2. BollingerBands
Three investment strategies were evaluated in this analysis. The first strategy involved investing once per year, however this approach was found to be suboptimal and is only recommended for the time period of 2019-2023. The second strategy involved investing in specific sectors that were determined to be more profitable. To implement this approach, an investor would use the BollingerBands strategy to analyze data from the previous year and identify the top three sectors with the greatest profitability. The investor would then invest only in these sectors for the following year. The process would be repeated each year to identify the top three sectors, and the sum of the investment would be divided between them according to a specific formula. The third strategy involved reinvesting each month, but this approach was not deemed to be the best strategy. Overall, there is significant potential for further improvement and optimization of these strategies.
3. TREND
To buy when it goes down for 5 days and sell goes up for 6 days. Well, the modified function performs much better. In my opinion, this strategy is less suitable for stable market, like from 2010 to 2019, but it performs better in the unstable market, where there is a lot of fluctuations of the price in the market. So my advice is to change between strategies according to the stability in the market.
4. MACD with rebalancing between different sectors each year.
Assuming that you invested $100,000 in each of the 11 ETFs listed at the beginning of 2010 and that all dividends were reinvested without using any strategy I would earn more money just investing the equal amount and not changing anything. So, even I have a profit it’s doesn’t mean that it’s a good strategy. More other, this is a gross profit – each trade also has a cost (trading fee), taxes, Inflation during the investment period can also reduce the actual profit earned. Maybe if use MACD with long term investment strategy, and various different factors (for example make changes according to the political map or stability in the market, in my opinion it could improve the results). We look at the profit not in the form of what We earned but what We could have earn. Ultimately, it is important to not solely focus on the profit earned but also consider the potential profit that could have been earned with a better investment strategy.
5. The strategies of buying stocks in September, after the New Year, and on Christmas are examples of seasonal investing strategies ( buying strategy )
In my opinion it's more speculation than investment, and low yield. Why did we want to check this strategy? Somewhere there is quite a lot of literature, various sayings that there is a “special days” for investing, like before or after the holidays. Does it have an effect? Maybe, but it seems that this “affect” is already included in the share price before the purchase. And this is definitely not the best way to invest. BUT it could give a hint to do more profound research, like to check the financial tweets, what happens before or after the holidays, something that could be interesting to know.
It is important to note that as previously mentioned, certain strategies may perform better in stable economic conditions, while others may perform better during times of fluctuations. Therefore, it is advisable to switch between these strategies based on the stability of the market. More than that, maybe combination of two strategies in one, like inflation and trend, can be a good strategy.
*Comparison of Trading Strategies - return percent.
