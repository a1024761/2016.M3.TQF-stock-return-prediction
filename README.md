# 2016.M3.TQF-stock-return-prediction
Project description:

From Fame-French three factor model, I got the instinction to implement short term multifactor in China's stock market. 
The aim of this project is to use machine learning knowledge to select efficient factors and test the return of the selected stocks.

See the proposal(https://github.com/PHBS/2016.M3.TQF-ML/blob/master/Proposals/Long%20shuyi.pdf)


Features:

1.Get close price and turnover data from 2014 to 2016 in China's SH stock market.

2.Delete the new stocks and only keep original stocks.

3.Factors:

  (1)MTM factor=(close[20]-close[0])/close[0]
  
  (2)average turnover rate=turnover[0:20].mean()
  
  (3)turnover change=average turnover rate[20]-average turnover rate[0]
  
  (4)average volatility=Var(close[0:20])
  
  (5)RSI:  RS=[A÷B]×100% (A:the sum of price increase among N days . B:the sum of price decrease among N days)
  
     RSI=100-100/(1+RS)

4.calculate the return of index

5.calculate the return of each stock and compare the return of stock and index

6.Using the n-th period as train set, and using the n+1-th period as test set. Then predict the return of n+2-th .

7.Select from the pool of stocks which is predicted to have higher return than index. Order all the stocks by RSI indicator and choose the smallest 10 stocks to buy it.And repeat this process every month.


Methods:

SVM/KNN


Implementation:

python notebook file :https://github.com/a1024761/2016.M3.TQF-stock-return-prediction/blob/master/final%20version.ipynb


Conclusion:

The accuracy of prediction varys between months. It's accuracy in some months can reach 0.9 but 0.3 for some other months.

The return of our strategy is good. For total three years ,the return of it is 609% and annual return is 82.6%. Compare with the index return ,it's effect is good. And it encounter a small withdraw in 2015 for the whole market is bad.
