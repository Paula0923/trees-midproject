# Trees
![Trees](images/trees-long-1.jpg)

## Overview
This project is part of the Ironhack Data Analysis Course (August 2024 - February 2025). In the project, I am analysing a **dataset on trees** in the Rostock area (Northern Germany). Among others, I will be looking at the following questions:
1. What kind of trees dominate?
2. What are the measurements of the trees?
3. Which trees are more often sponsored?
4. Which kind of trees are more often part of an alley?


## Data 
[**Here**](https://www.govdata.de/suche/daten/baume), you can take a look at the dataset. The data is provided by the Hanseatic and University City of Rostock. For this analysis, I am using the **dataset as of 5th December 2024**, the exact version can be found [**here**]("https://geo.sv.rostock.de/download/opendata/baeume/baeume.csv").
The dataset originally contains 13 columns and 71,139 rows. They are in German but are translated to English during my analysis (only those columns included for the analysis).
The data includes genus and species and the measurements of the trees, if they are part of an alley, if they are sponsored and the location (datatypes are continuous numerical and nominal categorial, some of the latter encoded in string and some in numbers (binary)).

## Repository Structure
    
    ├── dataframes                                  # data folder: cleaned dataset (df3).
    ├── images                                      # data folder: project image/graph files
    ├── 1_cleaning-trees.ipynb                      # code for cleaning process
    ├── 2_eda-trees.ipynb                           # code for EDA
    ├── 3_inferential-trees.ipynb                   # code for inferential statistics
    ├── metadata-trees.rdf                          # text file for meta data on dataset
    ├── presentation-trees.pdf                      # pdf with the project presentation
    └── README.md

## Approach
After cleaning the data, I proceeded with an **in-depth EDA** on a subset of the data. Following this, I conducted some **inferential statistical tests** on the interesting findings from the EDA section.

## Cleaning
The most challenging part in cleaning the data was some **unrealistically high data** entries regarding the measurements of trees (i.e. height of 814 metres). Because I could not find out the exact structural reasons for this (i.e. a missing decimal point), I replaced all unrealistic data with the **median** of the other entries in the specific tree species.

## EDA and Inferential Statistics: Findings
- The **height and trunk circumference** of trees are strongly positively correlated, this is not true for **crown diameter**.
- **Lime** trees reach the greatest heights and trunk circumference, **birch** trees have the lowest values regarding these two measurements and also the smallest diameters of crowns, here **maple** trees reach the greatest values.
- **Sponsored trees** are lower and have a smaller trunk circumference than non-sponsored trees.
- **Genus and alley** tree are significantly and strongly correlated: some tree genera are much more likely to be part of an alley than others. In absolute numbers, **lime** trees stick out, followed by **maple** trees. In proportional terms (share of trees which are alley trees within a genus), two trees have an even higher share than lime trees: The **Japanese pagoda** tree and the **maidenhair** tree.
- T tests showed that **sponsored trees are significantly lower and smaller** than trees without a sponsorship. Possible reasons for this are speculative but one could be that trees with a sponsorship **might be younger** (genus and sponsorship is not strongly correlated). Unfortunately, there is no data regarding the ages of the trees.
- Another set of t tests also showed that **alley trees are lower and smaller** than non-alley trees. As described before, if a tree is part of an alley or not **highly correlates with the genus**, so here we have an obvious reason for the highly significant results of the t tests.

In this [**trello board**](https://trello.com/invite/b/6751f9c08e8b980a0c723f23/ATTI1fa1a82074a3f6d8103801d41fe61d18E90ADF4D/trees), you can follow my thoughts and steps during the project process.
Please also find the **project presentation** in this repo for more insights.

![Trees](images/trees-long-3.jpg)