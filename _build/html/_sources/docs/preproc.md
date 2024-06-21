# Dataset and preprocessing

We used three data sets for this process. The most important data set is the life expectancy data set, which can be found at https://www.kaggle.com/datasets/amirhosseinmirzaie/countries-life-expectancy.
This data set is the main data set used for the life expectancy and vaccination columns. The second data set used is the GDP per capita data set, which can be found at https://www.kaggle.com/datasets/nitishabharathi/gdp-per-capita-all-countries. This dataset contains all gdp per capita for most countries for the past 30 years, this is mainly used for correlations that can be found between life expectancy and GDP per capita. The last dataset used is the education dat set, which can be found at https://data.worldbank.org/topic/education , information about the education level was extracted from this data set, this information consists of the number of children who attend primary and secondary school.

## Cleaning
Before we were able to merge these three files, some preprocessing was done. The edudata and GDP datasets have the years as variables, but the life expectancy dataset has the years as entries. To equalize this, the years in the gdp and edudata have been moved to the entries using melt. 
After all datasets had the same form, the two columns 'learning' and 'GDP' were first removed from the life expectancy data set. This was done because in the case of the learning column it was not clear how it was constructed, hence the edu dataset. The GDP column contains too many empty entries to be useful so we replaced it with the GDP data set. 
Before these datasets could be joined, the naming of countries had to be manually matched. An example of this is 'united kingdom' instead of 'united kingdom of Britain and northern Ireland'. The names were equalized across all the datasets and the choropleth map we used, this was done so that the data would be displayed nicely. 
The datasets were then joined using inner join on the variables ‘years’ and ‘country names’. This produces a table with the following values, 459200 rows × 23 columns

## Variable description

Nominal
Discrete
Country, Country Code, Indicator Name, Indicator Code,
Ordinal
Discrete
Status
Interval
Discrete
Year, Value
Ratio
Discrete
Population, Hepatitis B, Measles, Polio, Diphtheria, HIV/AIDS, infant deaths 
Interval
Continues
Life expectancy, Value
Ratio
Continues
GDP, Total expenditure, BMI, thinness 1-19 years,Alcohol