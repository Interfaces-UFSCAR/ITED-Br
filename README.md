# ITED-Br
The Interfaces Twitter Elections Dataset: Data from the 2022 presidential elections in Brazil, as referenced in the related article, regarding it's construction and characteristics.

The repository contains a collection of tweets IDs extracted from Twitter (X) during the Brazilian presidential elections in 2022, encompassing the post-election period and the event of the attack on the buildings of the executive, legislative, and judiciary branches in January 2023. Our data collections has 282 million dehidrated tweets of Jun 20, 2023 to Jan 31, 2024. Furthermore, our dataset have over 280 millions of accounts IDs and over 30 millions media IDs

## Data Organization
The Tweet-IDs are organized as follows:  
  
__1. Tweet-IDs files are stored in a folders tree expressed by this path:__
```
data/query/year/month/day/type/
```
* query: represents the name of search string used to obtain the data;*
* year: year of collected data;
* month: month of collected data;
* day: day of collected data;
* type: type of collected data*

> *More explained on the Article
  
__2.Inside each leaf folders have parquet files containing the IDs__  
  
__3.Each file have the following name struct__  

```
type-query-year-month-day.parquet 
```
or
```
type-subtype-query-year-month-day.parquet 
```
  
* type: type of collected data (tweets, users, media, replies, quotes)*
* subtype: type of interaction collected*
* query: represents the name of search string used to obtain the data;*
* year: year of collected data;
* month: month of collected data;
* day: day of collected data;

> *More explained on the Article

## How to Hydrate

### Hydrating using [Hydrator](https://github.com/DocNow/hydrator) (GUI)
Navigate to the [Hydrator github repository](https://github.com/DocNow/hydrator) and follow the instructions for installation in their README. As there are a lot of separate Tweet ID files in this repository, it might be advisable to first merge files from timeframes of interest into a larger file before hydrating the Tweets through the GUI. 

### Hydrating using [Twarc](https://github.com/DocNow/twarc) (CLI)
Many thanks to Ed Summers ([edsu](https://github.com/edsu)) and Github user [SamSamhuns](https://github.com/SamSamhuns) for writing this script that uses [Twarc](https://github.com/DocNow/twarc) to hydrate all Tweet-IDs stored in their corresponding folders. 

## More information
For more information about the dataset consider to read our article on 

# DOI
https://zenodo.org/doi/10.5281/zenodo.13124678

# Data Usage Agreement
This dataset is licensed under the Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International Public License (CC BY-NC-SA 4.0). By using this dataset, you agree to abide by the stipulations in the license, remain in compliance with Twitter’s Terms of Service, and cite the following manuscript:
Iasulaitis, S.; Valejo, A.D; Greco, B.C; Perillo, V.G; Messias, G.H; Vicari, I. The Interfaces Twitter Elections Dataset: Construction process and characteristics of Big Social Data during the 2022 presidential elections in Brazil. PLOS ONE (2024). (DOI)






