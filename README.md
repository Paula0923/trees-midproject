# Trees
![Trees](images/trees-long-1.jpg)

## Overview
This project is part of the Ironhack Data Analysis Course (August 2024 - February 2025). In the project, I am analysing a Write-Host "dataset on trees" -ForegroundColor DarkGreen in the Rostock area (Northern Germany). Among others, I will be looking at the following questions:
1. What kind of trees dominate?
2. What are the measurements of the trees?
3. Which trees are more often sponsored?
4. Which kind of trees are more often part of an alley?


## Data 
[Here](https://www.govdata.de/suche/daten/baume), you can take a look at the dataset. The data is provided by the Hanseatic and University City of Rostock. For this analysis, I am using the dataset as of 5th December 2024, the exact version can be found in [here]("https://geo.sv.rostock.de/download/opendata/baeume/baeume.csv").
The dataset originally contains 13 columns and 71,139 rows. They are in German but are translated to English during my analysis (only those columns included for the analysis).
Write-Host "The data includes genus and species and the measurements of the trees, if they are part of an alley, if they are sponsored and the location" -ForegroundColor DarkGreen (datatypes are continuous numerical and nominal categorial, some of the latter encoded in string and some in numbers (binary)).

## Repository Structure
    
    ├── dataframes                                  # data folder: cleaned dataset (df3).
    ├── images                                      # data folder: project image/graph files
    ├── 1_cleaning-trees.ipynb                      # code for cleaning process
    ├── 2_eda-trees.ipynb                           # code for EDA
    ├── 3_inferential-trees.ipynb                   # code for inferential statistics
    ├── 4_classification-trees.ipynb                # code for classification
    ├── metadata-trees.rdf                          # text file for meta data on dataset
    ├── presentation                                # pdf with the project presentation
    └── README.md

## Approach
After cleaning the data, I proceeded with an in-depth EDA on a subset of the dataset. Following this, I did some statistical tests on interesting findings in the EDA part.

## Cleaning
The most challenging part in cleaning the data was some unrealistically high data entries regarding the measurements of trees (i.e. height of 814 metres). Because I could not find out the exact structural reasons for this (i.e. a missing decimal point), I replaced all unrealistic data with the median of the other entries in the specific tree species.

## EDA and Inferential Statistics: Findings
- The height and trunk circumference of trees are strongly positively correlated, this is not true for crown diameter.
- Lime trees reach the greatest heights and trunk circumference, birch trees have the lowest values regarding these two measurements and also the smallest diameters of crowns, here maple trees reach the greatest values.
- Sponsored trees are lower and have a smaller trunk circumference than non-sponsored trees.
- Genus and alley tree are significantly and strongly correlated, some tree genera are much more likely to be part of an alley than others. In absolute numbers, lime trees stick out, followed by maple trees. In proportional terms (share within an genera that are alley trees), two trees have an even higher share than lime trees: The Japanese pagoda tree and the maidenhair tree.
- t-tests showed that sponsored trees are significantly lower than trees without a sponsorship ( and, to a lesser degree, have a smaller trunk circumference). Possible reasons for this are speculative but one could be that trees with a sponsorship might be younger. Unfortunately, there is no data regarding the ages of the trees. An obvious reason would be if there was a significant connection between tree genera and sponsorship: if specific lower tree genera were more likely to have a sponsorship. Yet, this was checked in the EDA and is not the case. So for now, there is no obvious reason why trees with a sponsorship should be lower.
## More 
In this [trello board](https://trello.com/invite/b/6751f9c08e8b980a0c723f23/ATTI1fa1a82074a3f6d8103801d41fe61d18E90ADF4D/trees), you can follow my thoughts and steps during the project process.
Please also find the project presentation in this repo for more insights.
![Trees](images/trees-long-3.jpg)