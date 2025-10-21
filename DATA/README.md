# Project Metadata

## 1. Data Summary
The Zillow Home Value Index (ZHVI) is a smoothed, seasonally adjusted estimate of the typical home value in U.S. dollars across different regions over time. The dataset includes regional metadata such as RegionID, RegionName, and State, followed by monthly ZHVI values spanning from January 2000 to August 2025 for each region, including the United States aggregate, and the corresponding metro area cities (New York, Los Angeles, Chicago, San Francisco, and Miami). Data was accessed through the Zillow API and bulk CSV downloads, with a copy stored in the project repository under `DATA/Metro_zhvi_uc_sfrcondo_tier_0.33_0.67_sm_sa_month.csv` in the DS4002 project folder. The dataset has a monthly temporal granularity and spatial granularity at the metropolitan statistical area (MSA) level, with additional coverage of national aggregates. All values are expressed in U.S. dollars.

## 2. Provenance
Zillow constructs the Zillow Home Value Index (ZHVI) from transaction and listing data, applying smoothing and seasonal adjustment to estimate typical home values at regional levels. The Zillow Home Value Index (ZHVI) data for this project was downloaded on October 8, 2025. Zillow updates this data monthly, typically on the 16th of each month. For this project, the focus on major metropolitan areas, including New York, Los Angeles, Chicago, San Francisco, and Miami, to capture diverse housing market behaviors across the United States. These metro-level series were extracted from the full national dataset and retain Zillow’s provided timestamps, which correspond to end-of-month markers.

## 3. License 
All original code in this project is released under the MIT license, allowing individuals to freely use, modify, and distribute with proper attribution. Use of Zillow datasets is governed by Zillow’s Terms of Use/Data Policies. Our usage is non‑commercial and academic. Redistribution and public display may be restricted so we will ensure compliance by limiting distribution to course submissions and properly attributing Zillow.

## 4. Ethical Statements
The dataset is aggregated at regional levels with no personally identifiable information. Still, forecasts can influence perceptions of affordability and investment. Therefore, we will avoid overstating precision, communicate uncertainty bands, and highlight limitations. These forecasts will not be used for credit, underwriting, or individual‑level decisions.

## 5. Data Dictionary
| **Column**     | **Description**                                                                                                      | **Potential Response** |
|----------------|----------------------------------------------------------------------------------------------------------------------|-------------------------|
| RegionID       | Unique numerical identifier assigned by Zillow for each geographic region.                                           | 394913                  |
| SizeRank       | Rank of the region based on market size within the dataset (0 = largest).                                            | 1                       |
| RegionName     | Name of the region represented in the dataset.                                                                      | New York, NY            |
| RegionType     | Geographic category of the region (e.g. country, msa).                                                              | msa                     |
| StateName      | Two-letter postal abbreviation for the state or region.                                                             | NY                      |
| Date           | Timestamp representing the end of each month for which ZHVI is reported.                                            | 2024-08-31              |
| ZHVI (USD)     | Smoothed, seasonally adjusted estimate of typical home value for that metro area, measured in U.S. dollars.         | 1,050,000               |

## 6. Explanatory Plots
- **Plot 1:** Absolute Home Values Across Major U.S. Metros Over Time
  ![Time series chart showing ZHVI growth](/OUTPUTS/eda_multicity_levels.png)
- **Plot 2:** ZHVI Year-over-Year (YoY) % Change
  ![Time series chart showing the annual rate of change of ZHVI](/OUTPUTS/eda_multicity_yoy.png)

