This analysis is based on data from Mapping Police Violence (2013-2026) for the state of California. Read their [full methodology here](https://mappingpoliceviolence.org/files/MappingPoliceViolence_Methodology.pdf).

Census places are used as the geographic scale as a compromise between County (too general geographically, but many other police-related datasets at this scale) and Census Tract (not enough data in the MPV to create statistics).

This repo and dataset was created to support a GIS project for PH277 and my masters of city and regional planning capstone at UC Berkeley College of Environmental Design.

Sources:
- “Mapping Police Violence,” Campaign Zero, Accessed February 2026, https://mappingpoliceviolence.org/
- US Census ACS 5-year 2020-2024, Table B03002

## Race and Ethnicity
Column names in this data use race categories from MPV, and map to Census definitions in the following way: 
| This repo | MPV | Census |
| --- | --- | --- |
| white | White | Non-Hispanic White |
| asian | Asian | Non-Hispanic Asian |
| black | Black | Non-Hispanic Black |
| hispanic | Hispanic | Hispanic or Latino |
| native | American Indian and Alaska Native | Non-Hispanic American Indian and Alaska Native |
| pi | Native Hawaiian and Pacific Islander | Non-Hispanic Native Hawaiian and Pacific Islander |
| unknown | Unknown race | Sum of Non-Hispanic Some other race and Non-Hispanic two or more races |
| poc | n/a | Sum of all non-white races |

## Disparity Calculation
Each race has an incident disparity rate as compared to the white baseline. Disparity rate is calculated by: 
$$(Group Incidents / Group Population) / (White Incidents / White Population)$$

Disparity rates are null if `total_incidents` is less than 5 for that Place. Disparity rates are set to a maximum of 20 when white incidents are zero and any race incidents are not zero - 20 is set instead of infinity. These min and max outlier variables can be changed in the `create_police_stats` notebook:
```
min_incidents=5
disparity_cap_value=20.0
```

## incidents_places_disparity_rates.csv data

- Each row is a unique Census Designated Place in California. These are described in the columns `PLACEFP` which is a Place's Census 5-digit FIPS code, and `NAME`.
- Each race category has Police Killing incidents per race, indicated with `_incidents`, in totals and percents. `_pct` at the end of a column name indicates a percent, as a percent of total incidents in that Place.
- Each race category has population data per race, indicated with `_pop`, in totals and percents. `_pct` at the end of a column name indicates a percent, as a percent of total population in that Place.
- Incident disparity rates for each race as compared to the white baseline, indicated with `_likelihood_vs_white`.
