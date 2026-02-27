This analysis is based on data from Mapping Police Violence. Read their full methodology here: https://mappingpoliceviolence.org/files/MappingPoliceViolence_Methodology.pdf

“Mapping Police Violence,” Campaign Zero, Accessed February 2026, https://mappingpoliceviolence.org/

Census places are used as the geographic scale as a compromise between County (too general geographically, but many other police-related datasets at this scale) and Census Tract (not enough data in the MPV to create statistics).

This repo and dataset was created to support a GIS project for PH277 and my masters of city and regional planning capstone at UC Berkeley College of Environmental Design.

The "incidents_places_disparity_rates.csv" file has the following data columns, for each Census Designated Place in California: 
- Police Killing incidents per race, totals and percents:
 'native_incidents',
 'asian_incidents',
 'black_incidents',
 'hispanic_incidents',
 'pi_incidents',
 'unknown_incidents',
 'white_incidents',
 'total_incidents',
 'poc_incidents',
 'native_incidents_pct',
 'asian_incidents_pct',
 'black_incidents_pct',
 'hispanic_incidents_pct',
 'pi_incidents_pct',
 'unknown_incidents_pct',
 'white_incidents_pct',
 'poc_incidents_pct'
- Population per race, totals and percents:
 'total_pop',
 'white_pop',
 'native_pop',
 'pi_pop',
 'black_pop',
 'asian_pop',
 'hispanic_pop',
 'unknown_pop',
 'poc_pop',
 'white_pop_pct',
 'native_pop_pct',
 'pi_pop_pct',
 'black_pop_pct',
 'asian_pop_pct',
 'hispanic_pop_pct',
 'unknown_pop_pct',
 'poc_pop_pct'
- Incident disparity rates for each race vs. white. Disparity rates are null if total_incidents is less than 5. Disparity rates are set to a maximum of 20 when white incidents are zero and any race incidents are not zero - 20 is set instead of infinity. These min and max outlier variables can be changed in the create_police_stats notebook.
 'native_likelihood_vs_white',
 'asian_likelihood_vs_white',
 'black_likelihood_vs_white',
 'hispanic_likelihood_vs_white',
 'pi_likelihood_vs_white',
 'unknown_likelihood_vs_white',
 'poc_likelihood_vs_white'
