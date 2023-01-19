# Utah:  A Time Study

## Business Understanding:  
##### Bluestone Investment Group is looking to expand its interests in the state of Utah.  Bluestone has tasked us with finding the top areas in the state with the best ROI.  Bluestone would like to see what the ROI in these areas would be for three and five years.  We will predict the top 5 zipcodes that Bluestone should invest in using time series modelling.

## Data Understanding and Preparation:
###### The data provided to us consists of information pertaining to over 14,000 Zip codes within the United States. The data is located within the ‘zillow_data.csv’ file in this repository. In total, there are 14,723 rows of data and 272 columns.  The data contained within the dataset includes information such as states, counties, cities, metros, zip codes, and values over time.  The project goal was defined by the business problem where our client was only interested in investing in homes within the state of Utah. To narrow down the best areas to invest in we looked at the state's counties first.
![counties](https://user-images.githubusercontent.com/96254640/213546506-e8031e03-0315-49d6-a162-3ca6b97a5c1f.png)
###### Here we can see that the top five counties with homes that have the highest mean value are Summit, Wasatch, Morgan, Salt Lake, and Utah counties.  Since the client was interested in zip codes, we looked at homes with the highest average mean value by zipcode.  Here is what we found:
![zipcode](https://user-images.githubusercontent.com/96254640/213561189-ec3882af-776c-4d6c-94e6-bbb6496009f9.png)
###### Here we see the zipc codes with the highest mean value homes.  Since the client is most interested in the highest return on investment in a relatively short amount of time, we will look at the top ten percent of zip codes with the highest average mean value, and create a model based off of the last ten years of data to forecast future home values.
