# Dataset and preprocessing

We have used a lot of datasets for this project, most of this data from different sources, such as Kaggle, World Bank Open and The World Health Organisation (WHO). From kaggle we got the original dataset containing the information for the life expectancy from [Kaggle](https://www.kaggle.com/datasets/amirhosseinmirzaie/countries-life-expectancy). 
The data for the vaccination and diseases come from [The World Health Organisation](https://immunizationdata.who.int/global?topic=&location=). All the other data is acquired from [The World Data Bank](https://data.worldbank.org/). This website contains data on a wide variety of topics, so we had enough to create our plots.

## Cleaning
Before we were able to merge the data sets that we used, we first had to equalize the format of the files. Most of the files had a source section at the bottom, which was manually deleted to avoid any potential problems. After this we had to make the format of the columns and rows to be equal, for this we used the melt and pivot functions. The Melt function was used to change the year's columns to rows, while the pivot function was used when different indicators were placed under one column. The pivot was primarily used to make the plotting easier, while the melt was used to merge more efficiently. Before these datasets could be merged, the naming of countries had to be manually matched. An example of this is ‘united kingdom’ instead of ‘united kingdom of Britain and northern Ireland’. The names were equalized across all the datasets and the choropleth map we used, this was done so that the data would be displayed nicely. We manually changed the names for the dataset used by the choropleth plot so the data would plot. All other times we used an import called pandas pycountry to change the country names. After this the datasets could be merged using the inner join function.

## Aggregation
When plotting we used aggregation, we used two types of aggregation, mean and normalization. We used mean when we had a lot of data like different countries or years and just wanted one data point. We used the normalization for the choropleth plot where the normalization aided the use of the gradient.

## Variable description

| **Measurement Scale** | **Status**   | **Variables** |
|-------------------|-----------|----------|
| Nominal           | Discrete  | Country, Country Code, Indicator Name, Indicator Code, Antigen |
| Ordinal           | Discrete  | Undernourishment |
| Interval          | Continuous| Year, Value |
| Ratio             | Discrete  | Population, Hepatitis B, Measles, Polio, Diphtheria, HIV/AIDS, Infant deaths, Life expectancy, Value, GDP, Total expenditure, BMI, thinness 1-19 years, Alcohol, Child mortality per 1000, GDP per Capita, School enrollment, primary (% gross), School enrollment, secondary (% gross), School enrollment, tertiary (% gross), total (% of relevant age group), amount of clean water |
