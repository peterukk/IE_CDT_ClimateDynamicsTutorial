# Climate Prediction $~~~~~~~~~~~~~~~$  tinyurl.com/bdcuw4ju 
Imagine you work for the Met Office and a client (e.g., from agriculture, utilities companies, finance) has asked you predict the temperature in Oxford, UK on 11th of December 2025 (a month from now), 11th November 2026 (a year from now) and on 11th November 2100. You have access to data from climate model simulations (CMIP) and reanalysis (ERA5) already downloaded from [the Climate Data Store (cds)](https://cds.climate.copernicus.eu/datasets/projections-cmip6?tab=download). 

Think about: 
* What data and methods would you use here?
* How would you approach the different timescales differently?
* Are there any assumptions you would make?
* What information would you provide to the client? 
* What sources of uncertainty do you expect in your prediction and how could you represent uncertainty?

There are two different notebooks. You can start with whichever exercises you prefer. The notebooks have more specific questions and assumed approaches, but you are welcome to approach the questions above in a more open-ended manner, also using data/models from another source if you wish. 

### Set up
You can use these notebooks in your local environment (some basic dependencies are required), or use Google Colab, which is the easiest way. Each notebook will have a Colab link associated with it. Colab doesn't host data, so you'll still have to pull the repo within Colab. 

## Time series approach

To predict the temperature at a specific location on 11th November 2026, we can use time series data to inform us about the historical temperatures in this location.

The jupyter notebook [PredictTimeseries.ipynb](PredictTimeseries.ipynb) will help you open the dataset. This data comes from a historical simulation of the Met Office coupled climate model UKESM. 

[Click here to open the notebook on Google Colab](https://colab.research.google.com/github/peterukk/IE_CDT_ClimateDynamicsTutorial/blob/main/PredictTimeseries.ipynb) 


## Spatial pattern approach

For longer term predictions in 2100, we need to consider global warming. Assume that in 2100, the global mean temperature will be ~1.5K warmer than today (or ~3.0K warmer than pre-industrial levels) [IPCC, 2021]. The jupyter notebook [PredictSpatialPatternSetup.ipynb](PredictSpatialPattern.ipynb) will help you open two climate model datasets: one from a pre-industrial climate simulation and one from a 4xCO2 climate simulation.

[Click here to open the notebook on Google Colab](https://colab.research.google.com/github/peterukk/IE_CDT_ClimateDynamicsTutorial/blob/main/PredictSpatialPatterns.ipynb) 

With a technique called "Pattern Scaling", you can interpolate between these two to estimate the global map of climate change for a given CO2 forcing scenario (Santer, 1990, Mitchell, 2003, Tebaldi & Arblaster, 2014). Pattern scaling assumes that the pattern of warming remains constant but scales linearly by a scaler variable, such as global mean temperature. The steps are:

1. Take temperature difference between two scenarios
2. Normalise pattern by global mean temperature change - this gives the pattern of warming per 1K of warming (so should be centered around 1).
3. Scale the pattern by the new global mean temperature change

How does the global warming pattern in GCM projections compare with ERA5?

## Other approaches

Think about other approaches you could take to predict the temperature at some time point in the future. How would you blend both temporal and spatial data to improve your predictions? How would you leverage AI/ML and what do you see as the strengths and potential withfalls with using ML approaches for predictions on weather versus climate timescales? 


## References
* Santer, B. D., Wigley, T. M., Schlesinger, M. E., & Mitchell, J. F. (1990). Developing climate scenarios from equilibrium GCM results.
* Mitchell, T. D. (2003). Pattern scaling: an examination of the accuracy of the technique for describing future climates. Climatic change, 60(3), 217-242.
* Tebaldi, C., & Arblaster, J. M. (2014). Pattern scaling: Its strengths and limitations, and an update on the latest model simulations. Climatic Change, 122, 459-471.
* IPCC, 2021: Summary for Policymakers. In: Climate Change 2021: The Physical Science Basis. Contribution of Working Group I to the Sixth Assessment Report of the Intergovernmental Panel on Climate Change [Masson-Delmotte, V., P. Zhai, A. Pirani, S.L. Connors, C. Péan, S. Berger, N. Caud, Y. Chen, L. Goldfarb, M.I. Gomis, M. Huang, K. Leitzell, E. Lonnoy, J.B.R. Matthews, T.K. Maycock, T. Waterfield, O. Yelekçi, R. Yu, and B. Zhou (eds.)]. In Press.

