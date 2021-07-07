# combot

# 1 First we want to Forecast metric one year ahead without variable changes

For this, we use the Recurrent neural network(RNN). It takes 7 days of clicks as an input and predicts the next day's click as output.

In the image below the yellow line is last year's click data and the blue line is the prediction of next year. 



With this method prediction made by model is not accurate so I am trying other alternative models for better outcomes

# 2 second We want to be able to change the metric/variable of Google Search Console’s Performance report to see how it affects the other metrics. For example, if we change the average position from 8.1 to 9 how it will affect all the other metrics one year ahead

For this task, we developed 4 models for each metric. All models use simple neural networks.
All the model takes three inputs and predicts the other column as output.
<code>
#   Date            Clicks	  Impressions 	CTR		    Position

1	  2021-06-07	    6412    	124682	      5.14%		  8.8
2	  2021-06-06	    4960	    112835		    4.4%	  	9.82
3	  2021-06-05	    4060  	  93446	      	4.34%		  9.38
4	  2021-06-04	    5094  	  112908		    4.51%	  	10.98
5	  2021-06-03	    5520    	123824      	4.46%		  10.54
6	  2021-06-02	    5940	    130603	      4.55%	  	10.91
7	  2021-06-01  	  6235    	127723	      4.88%		  9.32
8	  2021-05-31	    7160  	  134247	      5.33%	  	8.97
9	  2021-05-30	    5392	    111672    		4.83%		  9.87
10	2021-05-29  	  4556    	96625		      4.72%	  	9.36
11	2021-05-28	    5340  	  109453	      4.88%		  9.78
12	2021-05-27	    6246	    122663	      5.09%	  	9.61
13	2021-05-26  	  6318   	  118600		    5.33%		  9.14
14	2021-05-25	    5892  	  115586		    5.1%		  9.01
</code>
I use these 14 rows to test the model (unseen data)

Task 1 clicks prediction 
This model takes a list as an input [ <impressions>, <CTR>, <Position> ] and predicts clicks as an output.

The predicted values and actual values have a difference of 200 on average.

Task 2 impressions prediction  
This model takes a list as an input [ <clicks>, <CTR>, <Position> ] and impressions clicks as an output.

The predicted values and actual values have a difference of 1000 on average.

Task 3 CTR prediction
This model takes a list as an input [ <Clicks>, <impressions>, <Position> ] and predicts CTR as an output.

The predicted values and actual values have a difference of less than 0.01.

Task 4 position prediction  
This model takes a list as an input [<clicks>, <impressions>, <CTR>] and predicts position as an output.

The predicted values and actual values have a difference of 1 or 2.
#3 third Anomaly detection

In this, we use interquartile range(IQR) algorithms to detect anomalies.

These are clicks anomaly 


These are impressions anomaly



These are CTR anomaly

Ctr has no anomalies.


These are Position anomaly


Check update on development