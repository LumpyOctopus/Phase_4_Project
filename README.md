# Utah:  A Time Study

## Business Understanding:  
##### Bluestone Investment Group is looking to expand its interests in the state of Utah.  Bluestone has tasked us with finding the top areas in the state with the best ROI.  Bluestone would like to see what the ROI in these areas would be for three and five years.  We will predict the top 5 zip codes that Bluestone should invest in using time series modelling.

## Data Understanding and Preparation:
###### The data provided to us consists of information pertaining to over 14,000 zip codes within the United States. The data is located within the ‘zillow_data.csv’ file in this repository. In total, there are 14,723 rows of data and 272 columns.  The data contained within the dataset includes information such as states, counties, cities, metros, zip codes, and values over time.  The project goal was defined by the business problem where our client was only interested in investing in homes within the state of Utah. To narrow down the best areas to invest in we looked at the state's counties first.
![counties](https://user-images.githubusercontent.com/96254640/213546506-e8031e03-0315-49d6-a162-3ca6b97a5c1f.png)
###### Here we can see that the top five counties with homes that have the highest mean value are Summit, Wasatch, Morgan, Salt Lake, and Utah counties.  Since the client was interested in zip codes, we looked at homes with the highest average mean value by zip code.  Here is what we found:
![zipcode](https://user-images.githubusercontent.com/96254640/213561189-ec3882af-776c-4d6c-94e6-bbb6496009f9.png)
###### Here we see the zip codes with the highest mean value homes.  Since the client is most interested in the highest return on investment in a relatively short amount of time, we will look at the top ten percent of zip codes with the highest average mean value, and create a model based off of the last ten years of data in the zillow file to forecast future home values.  Here we can see that the zip codes 84060, 84098, 84004, 84020, and 84108 have the highest mean values over a ten year span.  What we do not see here is that the ROI on these zip codes is less than the top ten percent of zip codes.
![Top ten percent](https://user-images.githubusercontent.com/96254640/213577148-f3f3f11d-471e-4b65-9348-e2f43b59580e.PNG)
## Modeling
###### We will start modeling with the top ten percent of home values based on 3 and 5 year ROI assessments.  The initial model was based off of the 84119 zip code.
![model start](https://user-images.githubusercontent.com/96254640/213592113-c3b2edfc-15de-4027-8669-a897ea62620b.png)
###### Here we can see an upward trend on the 84119 zip code.  Since the housing market crashed in 2008, we will focus our model from 2008 onward.  Our first attempt at modeling was to use a SARIMAX model from scratch, but then used pmdarima to directly feed the data our raw series. This is because the SARIMAX model automatically does the differencing in our series for us to eliminate any trends or seasonality.
![download1](https://user-images.githubusercontent.com/96254640/213593195-e23c0263-98f0-4464-a3cf-c308a902f6da.png)
###### Here we can see by the histogram, our KDE line somewhat closely follows along the N(0,1) line which is the standard notation for a normal distribution having a mean of 0 and standard deviation of 1. This tells us that the residuals are normally distributed.  Our qq-plot displays that our residuals are following the linear trend line. This tells us that the residuals seen here are normally distributed.  From the Correlogram plot on the bottom left, we see that the time series residuals display low correlations with their lagged versions. This is clearer as we move further along the time series. This tells us there isn't obvious seasonality in our series.
![84229sarimax](https://user-images.githubusercontent.com/96254640/213596206-ce67d163-def2-40ff-ad38-7ad672fa256b.png)
###### Our model was able to forecast a reasonable trend on each of the top zip codes with the highest ROI.
## Conclusion
###### The top five zip codes to invest in given the problem are:
The top zip codes to invest in are:
##### 84116 with a 3 year ROI of 58.12% and a 5 year ROI of 73.83%
##### 84118 with a 3 year ROI of 51.33% and a 5 year ROI of 72.09%
##### 84119 with a 3 year ROI of 49.6% and a 5 year ROI of 65.53%
##### 84106 with a 3 year ROI of 49.49% and a 5 year ROI of 69.11%
##### 84401 with a 3 year ROI of 48.59% and a 5 year ROI of 54.39%
