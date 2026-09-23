# FHFA House Price Index: Real Estate Investment Data Exploration

**Author: Ozzie Shenk**

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ozzieshenk/Capstone.1.Shenk/blob/main/Capstone_1_Shenk.ipynb)

## 1. Understanding the Data

### When and Where Was the Data Acquired?

The dataset was obtained from the Federal Housing Finance Agency (FHFA) House Price Index. I accessed the data on September 23, 2026. The dataset contains housing price information from 1975 through 2026. It includes both quarterly and monthly observations.

The data covers several geographic levels across the United States. These include states, Metropolitan Statistical Areas (MSAs), U.S. Census Divisions, and Puerto Rico. In total, the dataset contains 472 unique geographic place names.

### How Was the Data Acquired?

The FHFA House Price Index is created using housing transaction data. The main Purchase-Only HPI uses sales price data from mortgages purchased or securitized by Fannie Mae and Freddie Mac. FHFA uses a weighted repeat-sales method, which compares the prices of the same properties when they are sold more than once over time. This helps measure changes in home values while controlling for differences between individual houses.

### Dataset Attributes

| Attribute | Description | Data Type |
|---|---|---|
| hpi_type | Type of House Price Index being reported | Nominal |
| hpi_flavor | Version of the HPI | Nominal |
| frequency | How often the observation is reported | Nominal |
| level | Geographic level of the observation | Nominal |
| place_name | Name of the geographic area | Nominal |
| place_id | Identifier for the geographic area | Nominal |
| yr | Year of the observation | Numeric / Interval |
| period | Month or quarter number within the year | Ordinal |
| index_nsa | House Price Index value that is not seasonally adjusted | Numeric |
| index_sa | Seasonally adjusted House Price Index value | Numeric |
| rstderr | Relative standard error associated with the estimate | Numeric |
| note | Additional information about the observation | Nominal / Text |

## 2. Data Summary & Initial Insights

The non-seasonally adjusted House Price Index (`index_nsa`) has a mean of 199.96 and a median of 172.13. The seasonally adjusted index (`index_sa`) has a mean of 216.67 and a median of 187.21. In both cases, the mean is higher than the median, suggesting that some relatively high index values pull the average upward.

### Missing Values

Most columns have no missing values. However, `index_sa` is missing 89,897 observations, or 48.33% of the dataset. The `rstderr` and `note` columns each have 127,791 missing observations, or 68.70%.

I would not automatically remove every row with a missing value because doing so would eliminate a large portion of the dataset. Instead, I would only filter missing observations when an analysis specifically requires those variables.

### U.S. House Price Trend

The U.S. House Price Index shows a clear long-term upward trend. Home prices increased steadily through the 1990s and early 2000s before declining after the mid-2000s housing peak. The index began rising again in the early 2010s and increased especially quickly after 2020.

The trend shows that housing values have generally increased over the long run, but the decline around the 2008 financial crisis also demonstrates that real estate prices can experience significant downturns.

## 3. Expanding My Investment Knowledge

### Additional Dataset: American Community Survey (ACS)

An additional dataset that would be useful for real estate investment analysis is the U.S. Census Bureau's American Community Survey (ACS). The ACS provides information about population, household income, employment, housing characteristics, and other economic and demographic factors.

The ACS complements the FHFA House Price Index because the two datasets measure different aspects of the housing market. FHFA mainly shows how home prices change over time, while the ACS provides information about the people and communities behind those changes.

For example, I could compare an area's home price growth with its population growth, household income, employment, or housing characteristics. Using both datasets could provide a more complete picture when evaluating a potential real estate investment.

**Dataset:** U.S. Census Bureau American Community Survey  
**Link:** https://www.census.gov/programs-surveys/acs/data.html

## 4. Conclusion

The FHFA House Price Index provides a useful way to see how U.S. home values have changed over time and across different geographic areas. The data shows a strong long-term increase in home prices, although there have also been periods of decline.

For someone considering a real estate investment, the HPI is helpful for identifying long-term price trends, but it should not be used by itself. Combining FHFA price data with economic and demographic information from a source such as the American Community Survey could provide a more complete picture of a market before making an investment decision.

## Data Source

Federal Housing Finance Agency (FHFA) House Price Index  
https://www.fhfa.gov/data/house-price-index
