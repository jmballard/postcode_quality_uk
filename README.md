# Postcode Quality in England

## Table of contents

- [Motivations](#motivations)
- [Data used](#data)
- [Visuals](#visuals)
- [Packages used](#packages_used)
- [Instructions](#instructions)
- [Files](#files)
- [Possible improvements](#improvements)
- [Credits](#credits)
- [License](#license)
- [Links](#links)
- [Status] (#status)

## Motivations and goals of this project <a name="motivations"></a>

The goal of this project is to create an analysis of the best postcodes to move into depending on freely available UK data.

The raw data is cleaned in a jupyter notebook file.

This project contains 2 code versions: 

- A version coded in R, using reticulate to read the pickle files and outputting a Shiny App.
- A version coded in Python, using a jupyter notebook to show the results.


## Data used <a name="data"></a>

For this analysis, I used freely available UK data (Links in section below). In particular, I used:

1. The Index of Multiple Deprivation Data from ONS
2. The Flood data from getthedata.com
3. Elevation and some pets data from data.world

All data are cleaned in the jupyter notebook "filter_raw_data.ipynb" to contain only english rows and necessary columns.



## Libraries used <a name="packages_used"></a>

### In Python

I used the following packages:

- pandas version 1.5.0
- numpy version 1.23.3
- os
- matplotlib version 3.6.0 (we import only matplotlib.pyplot)

### In R

I used the following packages:

- shiny
- shinyMobile
- shinyWidgets
- tidyverse
- leaflet
- leaflet.extras

## Instructions <a name="instructions"></a>

You can clone this repository by opening Git Bash and the command line

```text
git clone https://github.com/jmballard/postcode_quality_uk.git
```


## Files <a name="files"></a>

### filter_raw_data.ipynb

This notebook filters down the raw data to be able to push it into GitHub.

I filtered the columns to only be the ones necessary for the analysis. I only took the english postcodes.

To save more space, I downcasted the numerical columns. All files are saved in file "data/filtered".

I was able to cut down data size from 1.14GB to 88MB.

### create_main_data.ipynb

This notebook creates the main data used for this analysis.

It reads the different filtered tables, joins them, and saves the final table into a zipped csv file.



### postcode_quality_check.ipynb

This file is the Python version of this analysis. It returns some results depending on a postcode input.

The results given are:
- The name of the postcode, LSOA, District and Sector
- The risk of flooding of the postcode
- The elevation of the postcode
- The number of cats in the districts (with histogram and quantile on the country's distribution)
- The average number of dogs per household (with histogram and quantile on the country's distribution)
- A map where the postcode can be found
- The different IMD ranks

### postcode_quality_check.R

This file is the R version of this analysis. It returns some results depending on a postcode input.

The results given are:
- The name of the postcode, LSOA, District and Sector
- The risk of flooding of the postcode
- The elevation of the postcode
- The number of cats in the districts (with histogram and quantile on the country's distribution)
- The average number of dogs per household (with histogram and quantile on the country's distribution)
- A map where the postcode can be found
- The different IMD ranks

### Misc files

The other files are admin files:
- .gitignore: filters the files that will be pushed to GitHub
- LICENSE: the licence for this repo
- moving_postcode_filter.Rproj: The R project file to open Rstudio

### data folder
This folder contains 2 subfolders (only 1 in GitHub) and one file:
- Raw subfolder: containing the raw data sourced online. These files are too big to be pushed to GitHub.
- filtered subfolder: containing the cleaned and filtered data. Outputs of file "filter_raw_data.ipynb"
- main_data.zip file: main file used for analysis.

### venv folder
Folder containing the virtual environment for Python


## Possible improvements on this project: <a name="improvements"></a>

We could try to review automatically the houses on Rightmove using https://joeblogs.technology/2020/03/retrieving-data-from-rightmoves-api/ instead of reviewing manually a postcode.

## License <a name="license"></a>

MIT License

Copyright (c) [2022] [Julie Ballard]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.


## Links <a name="links"></a>

### Medium article linked to this project

https://medium.com/@bronnimannj/use-data-science-to-find-the-perfect-neighborhood-922631f69a04


### Links to data

- https://www.getthedata.com/flood-map/PE

- https://data.world/

- https://www.gov.uk/government/statistics/english-indices-of-deprivation-2019



### Interesting links to keep when trying to deploy the app

- https://joe-bologna.medium.com/how-to-make-an-r-shiny-progressive-web-app-cba06fdf97e0

- https://developers.google.com/web/tools/lighthouse/

- https://unleash-shiny.rinterface.com/mobile-pwa.html#handle-the-installation

- https://www.shinyapps.io/admin/#/signup


## Project status  <a name="status"></a>

This project is currently on stand by.