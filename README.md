# LSTM Stock Predictor - Analysis

## Technologies Used

* [Python](https://www.python.org)
* [pandas](https://pandas.pydata.org)
* [NumPy](https://numpy.org)
* [hvplot](https://hvplot.holoviz.org)
* [TensorFlow](https://www.tensorflow.org) - [LSTM](https://www.tensorflow.org/api_docs/python/tf/keras/layers/LSTM)

## Results

Of the two models tested, the model utilizing closing prices as the input resulted in slightly lower loss.  After 10 epochs, the sum of mean squared error was 0.0121.  Evaluating this model resulted in a loss of 0.0085.  On the other hand, the model based on the fear and greed index resulted in slightly higher error and loss: a sum of mean squared error of 0.0429 after 10 epochs and a model loss of 0.0706.




   ![closing-prices](images/closing_prices_first_try.png)                                           ![greed](images/Fear_and_Greed_first_try.png)                            
         
                Closing Prices                                 Fear And Greed Index




When graphing the predictions of these two models, closing prices appears to track the actual values better over time.  Fear and Greed results in predicted prices that are within $6,000 and $10,000, and usually close to $8,000.  As a result, these predicted prices are roughly $3,000 higher than actual prices up until about May.  At that point, they track fairly well for about a month, and then actual prices jump much higher than predicted prices, even though predicted prices show a slight rise.  

It’s also worth noting that while closing prices tracks better than Fear And Greed, it does not appear to have much predictive value.  In general, the price movement in the predictions happens after any movement occurs in the actual Bitcoin price.





![50epochs](images/Fear_and_Greed_50_epochs.png)

           Fear And Greed Index - 50 Epochs





In experimenting with some of the features of this neural network, I found that increasing the number of epochs from 10 to 50 resulted in a slightly better Fear and Greed Index model result.  The predicted values from June onward are much closer to the actual values (which rise up to over $12,000 and then fall back to around $10,000).  However, the predictions still do not model the actual values well before June.



   ![window1](images/window_1.png)                                    ![window5](images/window_5.png)    


          1 Window                                                          5 Windows


Tweaking the window size resulted in significant changes to the predictions values.  When the window size was set to 1, the predictions were nearly identical regardless of date.  As a result, the graph consisted of a line with a slope of almost 0 around the $5,400 price value.  As the window size was increased, the graph more closely resembled the original curve of predicted values.


