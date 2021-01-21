# Wine Price Study

#### Author: Steve Diamond [(GitHub)](ttps://github.com/ssdiam2000)

## Problem Statement

We, the members of the Data Science committee of the Princeton Wine Club, often sit in our local wine shops and wonder what we should try next. The questions that we ask ourselves include the following:
- Is it worth the price?
- Was this a good year for this wine variety, in this country, in this region?
- How important are the wine reviews they display with the wines?
- What are we really paying for?
    * The country prestige?
    * The region?
    * The variety?

Each time we go through this process, we start by thanking god that we only like red wine, greatly narrowing the scope of our search.

To gain a deeper understanding of the relationship between wine prices and these various factors, we are studying a dataset with over 70,000 red wines which was scraped from WineEnthusiast Magazine's website. The data includes many of the factors we are looking to explore along with pricing for each wine. Our team will use a series of regression techniques in order to:
- Better understand what factors are most important to determining price.
- Attempt to build a predictive model that can estimate the cost for a given bottle of wine

We will use Root Mean Square Error (RMSE) as our metric as we compare our models.

## Executive Summary

The pricing of wine is difficult for the buyer and we're never quite sure of the answers to the following questions:
- Is it worth the price?
- Was this a good year for this wine variety, in this country, in this region?
- How important are the wine reviews they display with the wines?
- What are we really paying for?
    * The country prestige?
    * The region?
    * The variety?

To gain a deeper understanding of the relationship between wine prices and these various factors, we did the following:

1. Data Gathering
    - We acquired a dataset of WineEnthusiast Magazine reviews that included over 70,000 red wines. This list was scraped by a fellow data scientist and posted on Kaggle.com.
2. Data Processing
    - Our team imported the entire dataset into a Pandas DataFrame and did the following steps of cleaning:
        - Narrowed the list to only red wines.
        - Removed unneccesary columns.
        - Imputed missing data for a limited number of datapoints by visiting the WineEnthusiast site and gathering data that was available.
        - Dropped rows which didn't have pricing.
        - Combined wine varietal categories where appropriate.
3. Exploratory Data Analysis
    - We used a variety of methods to discover broad trends in our data, inlcuding examinations of:
        * Data distribution.
        * Data correlations.
        * Review content analysis.
    - We did some unsupervised learning by doing a KPrototypes cluster analysis. Examine these clusters, we were able to better understand these wine groupings.
4. Modeling and Evaluation
    - We added the rusults of our KPrototypes clustering to the DataFrame for modeling.
    - We then used regression modeling, attempting to predict wine price, using RMSE as our metric.


### Table of Contents

#### [Data Cleaning/EDA Notebook with Links to the Following:](DataCleanEDA.ipynb)
- Loading Data
    - Library Imports
    - Data Imports
    - Data Dictionary
- Data Cleaning
    - Overview Analysis
    - Cleaning/EDA Needs by Column
    - Removing Non-Red Wines
    - Removing Columns
    - Imputing Data
    - Removing Additional Wines
    - Drop Non-Prices Rows
    - Variety Combinations
    - Winery Data
- Exploratory Data Analysis
    - Feature Engineering
        - Province & Region Data
        - Special Designation Column
        - Vintage Column from Title Column
    - Data Correlations
    - Data Distributions
    - Data Interations
        - Price vs Review Score
        - Cost-Per-Point Analysis
    - Review Word Frequency Analysis
    - Post-EDA Data Preparation
- Return To EDA

#### [KModes Notebook with Links to the Following:](kmodes.ipynb)
- Specific Links in Notebook

#### [Modeling-Conclusions Notebook](Modeling.ipynb)
- Modeling
    - Model Preparation
    - Models
        - Baseline Model
        - Linear Regression - Original Data
        - Linear Regression - KModes Data
        - Ridge Regression
        - LASSO Regression
        - Decision Tree Regression
        - Random Forest Regresssion
        - Extra Trees Regression
        - Feed Forward Neural Network
- Model Selection
- Model Evaluation
    - Residual Analysis
    - Coefficient Analysis/Interpretation
- Conclusion/Next Steps
- References

### Data Dictionary

|**Feature Name**|**Description**|
|:---|:---|
|country|Wine's country of origin|
|description|Wine review copy|
|designation|Part of wine name that separates this particular wine (i.e. Reserve)|
|points|Wine Enthusiast review score|
|price|Cost of wine (on the Wine Enthusiast site, this includes a link to buy)|
|province|Wine's province or state of origin (i.e. Provence, Califorinia)|
|region_1|Wine's specific region (i.e. Calistoga)|
|region_2|Wine's general region (i.e. Napa)|
|taster_name|Name of reviewer|
|taster_twitter_handle|Twitter information for reviewer|
|title|Full name of wine|
|variety|Grapes used to make the wine, sometimes called varietals|
|Unnamed: 0|Remnant column from saving without removing index|
|winery|Winemaker name|

## References
- https://www.kaggle.com/zynicide/wine-reviews
- https://www.winemag.com/
- https://www.wine-searcher.com/grape-varieties
- https://www.thewinecellarinsider.com/wine-topics/wine-educational-questions/abc-of-wine-glossary-of-wine-terms/
- https://en.wikipedia.org/wiki/Pinot_noir#Synonyms (example of wikipedia information used)
- https://data.library.virginia.edu/interpreting-log-transformations-in-a-linear-model/
