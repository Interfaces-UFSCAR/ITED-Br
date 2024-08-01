# ITED-Br

The Interfaces Twitter Elections Dataset (ITED-Br) encompasses data from the 2022 Brazilian presidential elections, as detailed in the related article discussing its construction and characteristics. The repository includes tweet IDs collected from Twitter (X) during the election period, the post-election phase, and the attack on the executive, legislative, and judiciary buildings in January 2023. Our dataset comprises 282 million dehydrated tweets, collected from June 20, 2023, to January 31, 2024. It includes over 280 million account IDs and more than 30 million media IDs.

## Data Collection and Organization

### Data Collection
The data was collected using the Twitter API, which provided academic/research access at the time. For the purposes of this repository, all the data except for the IDs representing the collected objects (such as tweets, users, media, replies, and quotes) was stripped, preserving the relationships between objects (e.g., tweets and their authors, retweets and their referenced tweets, etc.).

### Data Organization
The Tweet IDs are organized as follows:
__1. Tweet ID files are stored in a folder tree expressed by this path:__
```
data/query/year/month/day/type/
```
- `query`: represents the name of the search string used to obtain the data.*
- `year`: year of collected data;
- `month`: month of collected data;
- `day`: day of collected data;
- `type`: type of collected data*
*Detailed in the Article

__2. Each leaf folder has parquet files containing the IDs.__
__3. Each file has the following name structure:__
```
type-query-year-month-day.parquet
```
or
```
type-subtype-query-year-month-day.parquet
```
- `type`: type of collected data (tweets, users, media, replies, quotes)*
- `subtype`: type of interaction collected*
- `query`: represents the name of the search string used to obtain the data;*
- `year`: year of collected data;
- `month`: month of collected data;
- `day`: day of collected data;
*Detailed in the Article

__Obs:__ This repository's folder structure is for logical organization of the data only, and may not represent the ideal structuring for your particular use case or application. Also, our team found that avoiding large file sizes resulted in increased ease when it came to implementing optmized methods for processing data at a large scale.

## How to Hydrate

### What is Hydration?
Hydration is the process of re-fetching the full data of tweets (and other objects such as users) from Twitter (X) using their IDs. This is necessary because, due to restrictions on data sharing included in Twitter's terms of service, we can only freely share IDs, not the full tweet data. To obtain the full data, users need to rehydrate the objects using the X API (previously Twitter API).

It is possible to hydrate the data through any means that allow interaction with the API, which include, but are not restricted to: libraries for python or other programming languages, command line interfaces or apps with graphical user interface. We list some alternatives below, but they might not be the best option for your use case.

### Hydrating using [Hydrator](https://github.com/DocNow/hydrator) (GUI)
Navigate to the [Hydrator GitHub repository](https://github.com/DocNow/hydrator) and follow the instructions provided in the README. Due to the large number of separate Tweet ID files in this repository, it is advisable to merge files from timeframes of interest into a larger file before hydrating the tweets through the GUI.

### Hydrating using [Twarc](https://github.com/DocNow/twarc) (CLI)
Similar to Hydrator, but uses a command line interface. [GitHub repository](https://github.com/DocNow/twarc)).

## Structure

The following tables (which can also be found in our article) details the structure of each type of object that can be found contained in this dataset:

### Tweets

![Tweet properties](https://github.com/Interfaces-UFSCAR/ITED-Br/blob/main/tables/Tweets.png)

### Users

![User properties](https://github.com/Interfaces-UFSCAR/ITED-Br/blob/main/tables/Users.png)

### Media

![Tweet properties](https://github.com/Interfaces-UFSCAR/ITED-Br/blob/main/tables/Media.png)

### Interactions (e.g. Quotes, Replies)

![Tweet properties](https://github.com/Interfaces-UFSCAR/ITED-Br/blob/main/tables/Interactions.png)

## More Information

For more information about the dataset, please read our article:
- DOI: (PUBLICATION DOI PLACEHOLDER)

## Data Usage Agreement

This dataset is licensed under the Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International Public License (CC BY-NC-SA 4.0). By using this dataset, you agree to abide by the stipulations in the license, comply with Twitter’s Terms of Service, and cite the following manuscript: 
- Iasulaitis, S.; Valejo, A.D; Greco, B.C; Perillo, V.G; Messias, G.H; Vicari, I. The Interfaces Twitter Elections Dataset: Construction Process and Characteristics of Big Social Data During the 2022 Presidential Elections in Brazil. PLOS ONE (2024). (PUBLICATION DOI PLACEHOLDER)
