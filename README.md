# FHFA House Price Index: Real Estate Investment Data Exploration

**Author: Ozzie Shenk**

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ozzieshenk/Capstone.1.Shenk/blob/main/Capstone_1_Shenk_vF.ipynb)

## 1. Understanding the Data

### When and Where Was the Data Acquired?

The dataset was obtained from the Federal Housing Finance Agency (FHFA) House Price Index and was accessed on September 23, 2026. The Master HPI dataset contains observations ranging from 1975 through 2026, although the available time period varies depending on the specific HPI series.

The dataset covers several geographic levels across the United States. These include states, Metropolitan Statistical Areas (MSAs), U.S. Census Divisions, the United States as a whole, and Puerto Rico. The dataset contains 472 unique geographic place names.

### How Was the Data Acquired?

The FHFA House Price Index is created from housing transaction and mortgage data. One major series in the dataset is the Purchase-Only HPI, which uses sales price information from mortgages purchased or securitized by Fannie Mae and Freddie Mac. FHFA applies a weighted repeat-sales method that compares the prices of the same properties when they are sold more than once over time.

The Master HPI dataset also combines multiple HPI versions, or "flavors," so the exact data sources can differ depending on the series. This is important because the dataset does not represent one single type of housing-price observation.

### Dataset Attributes

The Master HPI dataset contains 12 attributes. Although some attributes are stored numerically in Python, the appropriate statistical treatment depends on what the variable represents.

| Attribute | Description | Data Type |
|---|---|---|
| hpi_type | Type of House Price Index being reported | Categorical - Nominal |
| hpi_flavor | Version or methodology of the HPI | Categorical - Nominal |
| frequency | Reporting frequency, such as monthly or quarterly | Categorical - Nominal |
| level | Geographic level of the observation | Categorical - Nominal |
| place_name | Name of the geographic area | Categorical - Nominal |
| place_id | Identifier for the geographic area | Categorical Identifier |
| yr | Calendar year of the observation | Temporal / Interval |
| period | Month or quarter within the year | Ordered Temporal |
| index_nsa | House Price Index, not seasonally adjusted | Quantitative / Continuous |
| index_sa | Seasonally adjusted House Price Index | Quantitative / Continuous |
| rstderr | Relative standard error of the estimate | Quantitative / Continuous |
| note | Additional information associated with an observation | Text |

## 2. Data Summary & Initial Insights

### Summary Statistics

Because the dataset contains categorical, temporal, and numerical variables, different summary measures are appropriate for different attributes.

| Attribute | Unique Values | Most Common / Range |
|---|---:|---|
| hpi_type | 5 | traditional |
| hpi_flavor | 3 | all-transactions |
| frequency | 2 | quarterly |
| level | 4 | MSA |
| place_name | 472 | United States |
| place_id | 472 | Identifier |
| yr | 52 | 1975 to 2026 |
| period | 12 | 1-12 monthly / 1-4 quarterly |

### Numerical Variables

| Attribute | Mean | Median | Mode | Minimum | Maximum | Range | Standard Deviation |
|---|---:|---:|---:|---:|---:|---:|---:|
| index_nsa | 199.96 | 172.13 | 100.00 | 18.60 | 1326.94 | 1308.34 | 116.13 |
| index_sa | 216.67 | 187.21 | 100.00 | 72.78 | 1043.20 | 970.42 | 113.51 |
| rstderr | 2.67 | 2.05 | 0.00 | 0.00 | 15.75 | 15.75 | 2.22 |

### Initial Observations

The summary statistics show that the Master HPI dataset contains several different types of housing price indexes, geographic levels, and reporting frequencies. Most observations are quarterly, and most geographic observations are reported at the Metropolitan Statistical Area (MSA) level. The dataset covers 472 unique geographic areas and observations ranging from 1975 through 2026.

For the numerical variables, the non-seasonally adjusted HPI (`index_nsa`) ranges from 18.60 to 1326.94, while the seasonally adjusted HPI (`index_sa`) ranges from 72.78 to 1043.20. These broad ranges reflect the fact that the Master dataset combines many different HPI series, locations, and time periods. Therefore, the overall means and medians are useful for describing the dataset, but they should not be interpreted as the average level of U.S. home prices.

To analyze housing-market trends more directly, it is more appropriate to examine a consistent HPI series over time, such as the national traditional purchase-only series used in the visualization below.

### Missing Values

Most variables in the dataset have no missing observations. However, `index_sa` has 89,897 missing values, representing 48.33% of the dataset. The `rstderr` and `note` variables each have 127,791 missing observations, or 68.70%.

Because such a large portion of these variables is missing, automatically deleting every row containing a missing value would remove a significant amount of data. A better approach would depend on the specific analysis being performed. For example, an analysis using `index_nsa` would not require removing observations simply because `index_sa` or `rstderr` is missing. Before imputing or deleting values, I would also investigate whether the missing observations are related to particular HPI series, geographic levels, or reporting frequencies.

### U.S. Purchase-Only House Price Index Over Time

Before creating the visualization, I examined the HPI series available for the United States. I selected the traditional, purchase-only, monthly series so that the graph follows one consistent measure over time.

The U.S. Purchase-Only House Price Index shows a clear long-term upward trend. The index increased steadily through the 1990s and early 2000s, declined following the mid-2000s housing-market peak, and began increasing again during the early 2010s. The rise becomes particularly steep after 2020.

From an investment perspective, the graph shows that housing values have generally increased over the long run, but the decline around the 2008 financial crisis also shows that real estate prices can experience significant downturns.

## 3. Expanding My Investment Knowledge

### Additional Dataset: American Community Survey (ACS)

An additional dataset that would be useful for real estate investment analysis is the U.S. Census Bureau's American Community Survey (ACS). The ACS provides information about population, household income, employment, housing characteristics, and other economic and demographic factors across different geographic areas.

This dataset would complement the FHFA House Price Index because the two datasets measure different parts of the housing market. The FHFA data mainly shows how home prices change over time, while the ACS provides information about the people and communities behind those price changes. For example, I could compare an area's home price growth with its population growth, household income, employment, or housing characteristics.

Using the two datasets together could provide a more complete view of a potential real estate investment. Instead of only seeing that home prices are rising or falling, I could also examine economic and demographic factors that may help explain those trends.

**Dataset:** U.S. Census Bureau American Community Survey (ACS)  
**Link:** https://www.census.gov/programs-surveys/acs/data.html

## 4. Conclusion

The FHFA House Price Index provides a useful way to see how U.S. home values have changed over time and across different geographic areas. The data shows a strong long-term increase in home prices, although there have also been periods of decline, including the housing-market downturn around the 2008 financial crisis.

For someone considering a real estate investment, the HPI is helpful for identifying long-term price trends, but it should not be used by itself. Combining FHFA price data with economic and demographic information from a source such as the American Community Survey could provide a more complete picture of a market before making an investment decision.

## Data Source

Federal Housing Finance Agency (FHFA) House Price Index  
https://www.fhfa.gov/data/house-price-index
