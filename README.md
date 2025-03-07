
# mongird-etal_2024

**Title:** High-resolution analysis of power plant land requirements for the evolving Western United States power grid indicates coordinated land use policies will be essential

**Authors:**
Kendall Mongird*, Cameron Bracken, Casey D. Burleyson, Konstantinos Oikonomou, Yang Ou, Jennie S. Rice, Travis Thurber, Nathalie Voisin 

\* corresponding author: kendall.mongird@pnnl.gov

![Projected Power Plant Sitings under Decarbonization](https://github.com/GODEEEP/mongird-etal_2024_tbd/blob/main/figures/fig_2_sitings_by_scenario_year_2050.png)

## Abstract

The expansion of the power grid will require unprecedented expansion of energy infrastructure, leading to extensive development footprints and land use conversion. Understanding where future power plant sitings are likely to take place and identifying the potential conflicts and land-use tradeoffs that may arise will be key to identifying feasible pathways and evaluating regional planning coordination needs. Through spatially explicit integrated modeling we develop projected 1 km2 resolution power plant sitings in the Western United States (US) for a business-as-usual scenario and an extreme load growth scenario – a net zero pathway. We find that 30% more land will be needed for solar and wind infrastructure to achieve a net zero economy compared to a business-as-usual economy and that 75% of that development is projected to be located within 10 km of natural areas. Additionally, we find California to be the most vulnerable Western US state to evolving siting constraints.

## Journal reference

[to be filled in upon publication]

## Data references
### Input data
|              Dataset              |                                   DOI                                    |
|:---------------------------------:|:------------------------------------------------------------------------:|
|  CERF GODEEEP Power Plant Sitings  |                          https://doi.org/10.5281/zenodo.13695663                              |
| GRIDCERF Geospatial Raster Layers |                     https://doi.org/10.57931/2281697                     |
|      GCAM-USA GODEEEP Output      |                 https://doi.org/10.5281/zenodo.10642507                  |
|  Renewable Capacity Factor Data   |                 https://doi.org/10.5281/zenodo.10214348                  | 

### Output data
The post-processed files (resulting from the analysis scripts itemized below) are are available at the following DOI.

|       Dataset       |                  DOI                   |
|:-------------------:|:-----------------------------------------------------------------------------:|
| Analysis Data Output |  https://doi.org/10.5281/zenodo.13698211 |


## Contributing modeling software
|  Model   | Version |         Repository Link          | DOI |
|:--------:|:-------:|:--------------------------------:|:---:|
| CERF |  v2.3.2   | https://github.com/IMMM-SFA/cerf | https://doi.org/10.5281/zenodo.7735212 |
| GCAM-USA |  v6.0   | https://github.com/JGCRI/gcam-core | https://doi.org/10.5281/zenodo.8010145 |
| reV |  0.7.1   | https://github.com/NREL/reV | https://doi.org/10.5281/zenodo.8247528 |
|   TELL   |  v1.1   | https://github.com/IMMM-SFA/tell | https://doi.org/10.5281/zenodo.8264217 |
|   GridView   |  v10.3.7   | N/A | N/A|


## Reproduce my analysis
Clone this repository to get access to the notebooks used to conduct the analysis. You'll also need 
to download the input files into the `data/input_data` directory. Each notebook that requires input data will specify where to download the data. 
Once you have the input datasets downloaded you can use the following 
notebooks to rerun the analysis and produce the post-processed data. 

To complete the analysis end to end, run the following notebooks:

| Script Type      |               Script Name               |                                                                       Description                                                                       |
|:-----------------|:---------------------------------------:|:-------------------------------------------------------------------------------------------------------------------------------------------------------:|
| Data preparation |    prepare_cerf_siting_output.ipynb     | Reads in and prepares CERF power plant siting output results for both the business-as-usual and net zero scenarios from the GODEEEP project experiment. |
| Data preparation |    prepare_retirment_output.ipynb     | Reads in and prepares power plant retirement output results for both the business-as-usual and net zero scenarios from the GODEEEP project experiment. |
| Data preparation |       prepare_raster_data.ipynb         |                           Prepares geospatial raster layers from the GRIDCERF database for western interconnection analysis.                            |
| Data preparation |         prepare_gcam_data.ipynb         |      Collects GCAM-USA results from the GODEEEP experiment and saves total generation by technology and state required in 2050 for each scenario.       |
| Data analysis    |      calculate_intersections.ipynb      | Calculates how much land from new power plant sitings in each scenario intersects with DACs, Important Farmland, and areas in close proximity to Natural Areas |
| Data analysis    |      calculate_dac_fossil_replacements.ipynb      | Calculates how many federally-identified DACs are projected to see both new renewable sitings and retirment of fossil fuel generation |
| Data analysis    | calculate_suitable_area_scenarios.ipynb | Calculates how much suitable land is available for solar and wind siting given different combinations of exclusions |
| Data analysis    | calculate_direct_land_use.ipynb | Calculates how much direct land is converted under different conversion assumptions. |
| Data analysis    | calculate_historical_solar_pv_capacity_density.ipynb | Calculates capacity density of existing solar pv installations in the western US |

## Reproduce my figures
Use the following notebooks to reproduce the figures in this publication.

| Figure Numbers |                Script Name                 |                                  Description                                   | 
|:--------------:|:------------------------------------------:|:------------------------------------------------------------------------------:|
| 1 |        plot_infrastructure_barplots.ipynb       | Barcharts of (1) new power plant capacity through 2050 by state and techonlogy and (2) land usage (km-squared) of new power plants through 2050 by state and technology |
| 2 |        plot_infrastructure_maps.ipynb           | Maps of new power plant sitings and retirements under each scenario |
| 3 |        plot_raster_intersection_maps.ipynb      | Maps of new and retired power plant sitings in each scenario on top of DACs, Important Farmland, and areas in close proximity to Natural Areas |                                                    
| 4 |        plot_renewable_suitability_maps.ipynb  | Plots the comparison of available generation for solar and wind siting by land exclusion scenario combinations |
| 5 |        plot_generation_suitability_comparison_charts.ipynb  | Plots the comparison of available generation for solar and wind siting by land exclusion scenario combinations |
