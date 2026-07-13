---
title: "The Threat of Displacement: Eviction Filing Patterns in Chicago"
excerpt: "For my Master's Capstone project, I explored the spatial patterns of eviction filings in Chicago and the property and household characteristics associated with higher eviction filing rates. I used a Local Moran’s I test to identify clusters of areas with statistically significant high and low eviction-filing rates. I also used a Tweedie regression model to examine associations between eviction filing rates, median property value, and the number of households with children in a census tract."
collection: portfolio
---

**Date:** June 2026

**Tools Used:** ArcGIS Pro, Python (Pandas, GeoPandas), Microsoft Excel for Data Analysis and Visualization 

**Capstone Research Project:** M.A. in Sustainable Urban Development, DePaul University

# Overview

I explored the spatial patterns of eviction filings in Chicago and the property and household characteristics associated with higher eviction filing rates. To achieve this, I combined eviction, demographic, housing, and property value data to construct three census tract-level datasets for 2010, 2015, and 2019. 

I used a Local Moran’s I test to identify clusters of areas with statistically significant high and low eviction-filing rates. I also used a Tweedie regression model to examine associations between eviction filing rates, median property value, and the number of households with children in a census tract. 

The results revealed that high eviction filing rates are concentrated in Chicago’s South and West sides, which are predominantly Black and economically disadvantaged communities. I also found that higher property values are associated with lower eviction rates, while an increase in the number of households with children in a census tract is associated with a higher risk of eviction. 

# Skills Demonstrated

**Geospatial Data Processing:** Utilized GeoPandas to create an original dataset that contains census data, the eviction rate, and property values for each census tract in Chicago.

**Spatial Autocorrelation Testing:** Created three maps in ArcGIS that show statistically high eviction rates were clustered in underinvested communities on the South and West sides of Chicago

**Tweedie Regression Analysis:** Conducted multiple Tweedie regression analyses in Python to discover that an increase in the number of households with children is associated with an increase in a neighborhood’s eviction rates. 

**Research and Policy Analysis:** Analyzed the Cook County eviction process and current eviction studies to ensure my reserach is in conversation with existing eviction literature. 

# View My Full Paper
The following is an abbreviated version of my capstone research. To see the full paper, which includes citations, a literature review, and a more in-depth analysis of my results, [click on this link.](/files/threat-of-displacement.pdf)


# Introduction:

There is a reason we call it the housing **crisis**. Living without permanent shelter has disastrous effects on one’s mental and physical health, access to employment opportunities, and community relations. Tenants are reminded of the housing crisis at the beginning of every month and at the end of every lease.  If a tenant fails to pay rent each month, they face the risk of eviction: the lawful removal of tenants from a rental property by the landlord. However, eviction is a legal process, and tenant removal is not always the final outcome. Tenants do not need to be forced out of their homes to be harmed by evictions. 

***Eviction filings*** are the stage of the process in which a landlord files a lawsuit to potentially remove a tenant. Most eviction filings do not end with tenant displacement. Missed rent is the most common reason a landlord will file for eviction, but they are hesitant to proceed with tenant removal.  Evictions are expensive lawsuits, and they have to pay for a lawyer and legal fees. Additionally, landlords often charge late-rent fees, creating a second source of revenue. Landlords also admit that filings dissuade tenants from making maintenance requests: you’re less likely to complain about a broken air conditioner if you could legally be kicked out.

Research finds that Black renters and households with children have a high eviction risk. A national analysis of the US evicted population found Black renters were the only racial group overrepresented in eviction filings. They were 18 percent of all renters, yet were 51 percent of those threatened with eviction. Adult renters living with at least one child had an annual filing rate of 10 percent, while adults without children had a rate of 5 percent. Black mothers had an annual eviction filing rate of 28 percent.  Between 2007 and 2016, children were present in 52 percent of households that received an eviction filing. Additionally, some studies have found that evictions are more common in poorer, underinvested neighborhoods. 

This project builds on this existing research and explores it in the Chicago context. I explored two research questions: the spatial pattern of eviction filings in Chicago and which property and household characteristics are associated with higher eviction filing rates.

## Research Question 1

*Are there clusters of census tracts with high and low eviction filing rates in Chicago? If so, what are the differences between demographics, housing costs, and income between these clusters?*

I used ArcGIS Pro to run a Local Moran’s I analysis to identify clusters and outliers among census tracts with high and low eviction filing rates.  After running this test, I created a table comparing eviction filing rates, housing, income and demographic characteristics between the high- and low-rate clusters. 

## Research Question 2

*What is the relationship between a census tract’s eviction filing rate, median assessed property values, and the percentage of households with children?*

I used a Tweedie Regression model to investigate the relationships between a census tract’s eviction filing rate, median assessed property values, and the percentage of households with children. Eviction filing rates are my dependent variable; median assessed property values and the percentage of households with at least one child are my independent variables. 

# Data Overview:

## Eviction Data

The eviction rate data come from the Lawyers’ Committee for Better Housing’s (LCBH) eviction data portal, which contains 225,710 residential eviction cases filed in the City of Chicago during 2010-2019. City of Chicago. The main variable of interest in this paper is the Eviction Filing Rate, which the LCHB defines as the number of eviction filings per 100 rental units in a census tract.

## Housing, Income, and Demographic Data

The data on housing, income, population, education, and racial demographics came from the American Community Survey (ACS) 5-year Estimates from 2006-2010, 2011-2015, and 2015-2019. Key variables include population, racial demographics, household characteristics, income, employment, housing status, and measures of rent.

## Median Assessed Property Value

The property value data comes from the Cook County Assessor’s Office Open Data Portal, which provides the land, building, and total assessed values for all Cook County parcels since 1999. The data were filtered to create three datasets listing parcel values for townships adjacent to Chicago for the tax years 2010, 2015, and 2019. I define assessed property value as the Board of Review Certified Total Value, which the County defines as a parcel’s combined land and property values that have been assessed by the Cook County Board of Review.

# Data Management Workflow

In Python, the eviction, ACS, and property value data were combined to create three unique datasets: one for each year (2010, 2015, and 2019). Each row in the data represents a Chicago census tract, and any census tract with a total population of 0 was removed. The final number of census tracts in my study is 797 for the 2010 data, 798 for the 2015 data, and 798 for the 2019 data. The ACS data required normalization, and I created percentage-based variables by dividing the population of interest by the total relevant population. For example, the percentage of the population that is Black was calculated by dividing a census tract’s total Black population by its total population. 

The property value data was clipped to the Chicago boundaries to include only parcels within the city. Then, parcels with an assessed value of zero were removed from the data set (these parcels were 1.51% of the 2010 parcels, 1.4% of the 2015 parcels, and 2.51% of the 2019 parcels). These parcels were then grouped by census tract to determine the median assessed property value for each tract in Chicago, which will serve as the property-value variable in the analysis.

# Results

## City-wide Eviction Filing Rates

![Figure 1](/images/Figure1.png "Figure 1")

![Table 1](/images/Table1.png)

First, I explored the Chicago-wide eviction filing rate for each year from 2010 through 2019. Figure 1 shows the Chicago-wide eviction filing rate for each year from 2010 to 2019. The red markers are the average eviction rate, and the grey area represents a range of possible rates. Filing rates started at 4.3 in 2012, peaked at 4.65 in 2012, then decreased each year until reaching a low of 3.09 in 2019. Table 1 shows the measures of central tendency and variance of Chicago’s filing rate. Each year has a large standard deviation, indicating that filing rates among census tracts are farther from the city-wide rate. The median filing rate is lower than the average rate in each year of the dataset, suggesting that high-rate outlier tracts are skewing the city-wide average to the right: eviction filings look very different depending on where you live.


## Spatial Pattern of Eviction Filing

The results of the Local Moran’s I analysis show that eviction filing rates are not randomly distributed across Chicago in 2010, 2015, and 2019. Figures 2, 3, and 4 show clusters of census tracts that have statistically significantly high or low eviction filing rates. The light red areas are high-rate clusters, and the light green areas are low-rate clusters. The dark red areas are high-rate outlier tracts near low-rate clusters, and the dark green areas are low-rate outlier tracts near high-rate clusters.

![Figure 2](/images/Figure2.png)
![Figure 3](/images/Figure3.png)
![Figure 4](/images/Figure4.png)


High filing rates are clustered almost exclusively on the South and West sides of the city and become increasingly concentrated there over time. The majority of tracts in the low-rate cluster are on the North Side of Chicago, but some are on the West and South Sides as well. Across all three years, the South-side tracts in the low-rate cluster are located in the Armour Square, Bridgeport, McKinley Park, and Archer Heights community areas. The West-side low-rate tracts are found in the West Town, South Lawndale, Lower West Side, and Near West Side community areas. Low-rate tracts in the Central part of the city are all located in the Near North Side community area. In 2010, there was a small high-rate cluster on the Northwest Side of the city. There are two tracts in this cluster, located in the Hermosa and Belmont-Cragin community areas.


## Demographic, Housing, & Income Differences Between Clusters and Outliers

![Table 2](/images/Table2.png)

Table 2 shows the income, housing, and demographic differences between the two cluster types, listing the median value of each sample. The saying “There’s only one map of Chicago” rings true here: the historic, racist disinvestment of the South and West sides is present in these results. These findings indicate that tracts in the high-rate cluster face a greater economic disadvantage than their low-rate counterparts: they have lower median household income, lower median owner-occupancy rate, higher median unemployment rate, and higher median rent-to-income ratio. 

Rents may be cheaper in the high-rate cluster, but not by much: the largest difference in median rent is $370. The median property value in the high-rate cluster is less than half that in the low-rate cluster, and the median rent-to-income ratio is at least 10 points higher. In the high-rate clusters, the median percentage of the population that is Black never falls below 94%. In the low-rate cluster, the median percentage never reaches 3.5%. Across all three years, the median percentage of households with children is higher in the high-rate cluster than in the low-rate tracts. 

![Table 3](/images/Table3.png)

However, the differences between the Outlier tracts in Table 3 show the opposite: the low-rate outliers appear to be at a greater economic disadvantage than the high-rate ones. Low-rate outliers have a higher median rent burden, higher unemployment, lower property values, and lower college attainment than high-rate outliers. The low-rate tracts have larger Black populations and more households with children, excluding 2019.  More research is needed to understand why these tracts have lower filing rates despite greater economic disadvantage. Investigating the housing options in high-rate outliers may prove interesting: these tracts may have litigious landlords.

## Tweedie Regression Results
I used a Tweedie Regression model to investigate the relationships between the eviction filing rate, the median assessed property value, and the percentage of households with at least one child in a census tract. Median household income, the percentages of vacant and owner-occupied housing units, and the median rent-to-income ratio are my control variables. The dependent variable is log-transformed, so we interpret the results as a percent change in the dependent variable.

![Table 4](/images/Table4.png)
![Table 5](/images/Table5.png)
![Table 6](/images/Table6.png)

Both independent variables had statistically significant p-values in each year of data tested. I must reject the null hypothesis that property value and households with children are unrelated to eviction filing rates, while holding income, rent, and housing variables constant.

Property values are negatively associated with a tract’s eviction filing rate. For every $1,000 increase in the median assessed property value, the eviction filing rate drops by 3.7 percent, 2.8 percent, and 3 percent. Areas with higher property values are wealthier, and tenants who can afford to live in wealthier areas are less likely to miss rent payments.

The percentage of households with children is positively associated with eviction filing rates. For every 1% increase in the number of households with at least one child, eviction filing rates increase by 62%, 162%, and 92%, respectively. This increase seems incredibly large, but the variable is the percent of households with at least one child. In a tract with 1000 households, 10 childless homes would have to have a baby to create a 1 percent increase. This is a major economic and demographic change for the census tract, which explains the massive increase in the filing rate.

# Conclusion

This research shows that Chicago’s most vulnerable communities deal with a high risk of forced displacement. The people living in high-rate areas are predominantly Black, and due to historic disinvestment, these communities have lower incomes, lower property values, and higher rent burdens than areas with low filing rates. Not only do high-rate neighborhoods have more households with children, but the decision to have a child is associated with higher filing rates. 

Victims of eviction may not be able to pay rent and are being punished for it. This problem is intensified by the housing crisis: there is a nationwide shortage of 7.3 million rental and 3.8 million owner-occupied units. This lack of housing supply is one of the contributing factors to rising rents. The ability to pay rent depends on two factors: the amount of money you have and the rent price. Victims of eviction in Chicago may be crushed by both.
