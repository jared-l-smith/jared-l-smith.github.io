---
title: "SRO Sales in Rent Burdened Areas"
excerpt: "This project analyzes the status of Chicago’s single‑room occupancy (SRO) housing since the passing of the 2014 SRO Preservation Ordinance. I integrated parcel‑sale and rent‑burden data to map where SRO losses intersect with areas of highest housing vulnerability.'>"
collection: portfolio
---

**Date:** June 2024  
**Tools Used:** Arc GIS Pro

This project analyzes the status of Chicago’s single‑room occupancy (SRO) housing since the passing of the 2014 SRO Preservation Ordinance. I integrated parcel‑sale and rent‑burden data to map where SRO losses intersect with areas of highest housing vulnerability.

### Skills Demonstrated:
**Data Sourcing & Preparation:** Researched the appropriate dataset to map parcel sales and isolated relevant SRO sales, ensuring accuracy in the final analysis. 

**Geospatial Data Management:**  Integrated parcel‑sale records with geocoded parcel shapefiles, allowing me to map the location of sold SROs. 

**Spatial Data Visualization:** Designed a choropleth map displaying rent-burden data across Chicago’s zip codes, translating data patterns into insights about affordability risks.

# Introduction: 

Single-room occupancy (SRO) hotels offer minimally furnished rooms for daily, weekly, and monthly rates. These rooms do not require a lease. SROs are often used as transitional housing for people facing homelessness. They serve as the "last resort" housing before complete homelessness and as the "first step" for someone transitioning into permanent housing.

Despite their importance, SROs are disappearing as private developers purchase and convert them into market-rate apartments, displacing residents. To address this, in December 2014, the City Council passed the SRO Preservation Ordinance, aiming to keep SRO housing available. Under the ordinance, SRO sellers must allow only affordable housing developers to purchase for a 6-month priority period before private developers can bid, and all developers must ensure displaced residents are relocated to affordable housing before the sale finalizes.

Transitional housing remains a vital resource for at-risk populations, and risk levels vary by community. One important measure is rent-burden: a household is considered rent-burdened when the rent exceeds 30% of income. This financial strain puts renters in a precarious position: when a major unexpected expense arises, they may not be able to afford rent. When the median rent of an area exceeds 30% of its median household income, that entire area is considered rent-burdened. 

This project examines the state of SROs in the communities where need is greatest. Since 2014’s SRO Preservation Ordinance, how many SROs have been sold in rent-burdened zip codes?

# Data:

**Rent-Burden Data**: 2023 American Community Survey: 5-Year Data [2019-2023, Block Groups & Larger Areas], Median Gross Rent as a Percentage of Household Income

**SRO Sales:** Cook County Government Open Data Portal, Cook County Assessor’s Office - Parcel Sales

# Workflow

The Cook County Assessor's Parcel Sale Dataset tracks all taxable parcel sales in Cook County, organized by date sold, seller, buyer, and land class. Land class is a numbered code that designates the parcel's land use, including a specific code for SROs. I filtered the data to create a list of SROs sold after December 2014. 

However, this SRO data was not georeferenced. To map SRO locations, I joined the data with Parcel Shapefiles from the Assessor’s Office Data Portal. 

After mapping SROs, I incorporated the rent burden data from the 2019-2023 American Community Survey by joining it with georeferenced zip code shapefiles. This process created a choropleth map of rent burden across Chicago, contextualizing the SRO data by community need.

# Results and Analysis 
![SRO Sales in Rent Burdened Areas](/images/sro-map.png)

The lowest recorded rent-to-income percentage in any Chicago zip code is 22.9%. Six zip codes are dedicating somewhere between 39.6% - 51% of thier income to rent payments. 

Since the 2014 Ordinance, 18 SROs have been sold, four of which are located in rent-burdened zip codes. Seven SROs were sold in zip codes near the rent-burdened threshold (within 2 percentage points of 30%). Notably, Zip Code 60640, including the Uptown community area, is approaching rent-burdened status and has lost 3 SROs since 2014, signaling increased risk to local affordability. 

Rent burden is one indicator of displacement risk, and this map represents only part of a complicated phenomenon. However, the results are concerning: most SROs sold were in areas where renters already pay a high share of income toward rent, or are close to doing so. SROs are just one type of transitional housing; expanding Chicago's affordable housing supply citywide is crucial to better address displacement risk. 

# Intrested in Learning More?
This project is part of my research into Single-Room Occupancy housing in Chicago’s Uptown neighborhood. My work explores the complicated history of SRO hotels and their role in preventing complete homelessness, despite their poor living conditions. This project investigates the history of SRO housing in Uptown, analyzes the area's wealth and demographic data, and presents policy solutions to ensure transitional housing remains under the control of local affordable housing developers and advocacy organizations. 

[You can download the paper at this link.](/files/Uptown-sro-analysis.pdf)
