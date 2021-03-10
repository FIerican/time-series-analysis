## Navigation

This README.md will be the source of information for navigating through the repository.

* `notebook.ipynb`: jupyter notebook with technical analysis
* `zillow_data.csv`: contains dataset used for analysis
* `images` folder: contains visualizationsimage


## Introduction: Business Opportunity

A real-estate investment firm has reached out for consultation on deploying capital into single family residences and how much to expect in future returns.

Their investment profile:

* not restricted to any specific geographic location
* no rural regions, must be in/near a metropolitan area
* maximize current low mortgage rate environment (no jumbo loans)
* stable markets that do not experience huge price fluctuations
* zipcodes that haven't experienced a significant value appreciation within last 2 years

The notebook will analyze data provided by Zillow (zillow.com/research/data/) to find 5 zipcodes that fit the criteria and project the appreciation rates for these zipcodes.


## Approach

To narrow down the possible investment opportunities before running a time series model, I looked at features like:
* the relative size of the zipcode (`SizeRank`)
* maximum conforming loan limits by zipcode
* the standard deviation and mean of the price over time
* appreciation rates (ROI) over last 2 years

## Findings - highlights

![Data Statistics](/images/statistics.png "Data Statistics")

> Within the top 20% of urbanized areas, states like California and Texas have the most zipcodes. States with the fewest zipcodes represented in the dataset are the more rural areas, like Vermont, South Dakota, and Alaska


![SortByAppreciation](/images/zipcodes-appreciation.png "Sorted by Appreciation")

> Top 5 and Bottom 5 zipcodes of filtered data, sorted by appreciation over the last 2 years


![SortByCVRatio](/images/zipcodes-cvratio.png "Sorted by CV Ratio")

> Top 5 and Bottom 5 zipcodes of filtered data, sorted by the CV ratio (the CV Ratio is the standard deviation divided by the mean)


![HighestPredictions](/images/highestpredictions.png "Highest Predictions")

> Blue highlights the zipcodes with the highest forecasted appreciation, based on prediction values


![SmallestCIDelta](/images/highestpredictions.png "Smallest Confidence Interval Delta")

> Purple highlights the zipcodes with the highest forecasted appreciation, based on smallest non-negative 95% confidence interval spectrum


###### *Further analysis is viewable in the `timeseries_analysis.ipynb` notebook and/or the `presentation.pdf` slide deck.*


## Conclusion

![Recommendations](/images/recommendations.png "Recommended Investments")


Given zipcode 29605 (Greenville, SC) has a high forecast price appreciation, albeit a large 95% confidence interval, it is worth investing in this zipcode, as the worst projected return is 27.2%.

By this same reasoning, zipcode 49505 (Grand Rapids, MI), zipcode 29607 (Greenville, SC), zipcode 38018 (Memphis, TN), and zipcode 46260 (Indianapolis, IN) are all worth investing in, as the worst projected return is within single digits.


## Future Opportunities

Further exploration can be conducted on further parameter tuning of the ARIMA models used to forecast  price appreciation.

Other opportunities are available in exploring different filtering techniques and other considerations like different features that could contribute to predicting the future value of properties (like neighborhood crime rate, average sq. ft. size, etc.)
