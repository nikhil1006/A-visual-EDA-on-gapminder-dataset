# A visual analysis of gapminder dataset

## Abstract

The visual analysis of gapminder dataset is a short exploratory data analysis project which deals with visual exploration of the dataset and drawing insights about the dataset.

## Introduction

### About the dataset

The gapminder dataset is maintained by the *[Gapminder foundation](https://en.wikipedia.org/wiki/Gapminder_Foundation)*. Gapminder Foundation is a non-profit venture registered in Stockholm, Sweden, that promotes sustainable global development and achievement of the United Nations Millennium Development Goals by increased use and understanding of statistics and other information about social, economic and environmental development at local, national and global levels.

Gapminder was founded in 2005 by Ola Rosling, Anna Rosling Rönnlund and Hans Rosling.[2] The name Gapminder was derived from the "Mind the Gap" warning messages on the London Underground.[3]

### Aims of the project notebook

This R notebook emphasizes the usage of basic exploratory analytical yechniques to visualize and draw useful insights from the gapminder dataset.

## Before getting started

The gapminder dataset is native to R and can be installed through R command line using the following commands.

```r
# Load the gapminder package
install.packages("gapminder")
library("gapminder")
```

To use gapminder dataset with python please refer to this [link](https://pypi.org/project/gapminder/)

To install R-kernel in anaconda, open anaconda prompt and type the following command
`conda install -c r r-essentials` Build R notebooks using *google colab* through this [link](https://colab.research.google.com/drive/1BYnnbqeyZAlYnxR9IHC8tpW07EpDeyKR). 

## Getting Started

Before we can work with the gapminder dataset, we'll have to load two R packages that contain the tools for working with it, then display the gapminder dataset, so that you can see what it contains. The package that we use for this project is *tidyverse* which is a collection of multiple packages such as *ggplot2, dplyr, data.table* etc.

```r
# Load the tidyverse package
library(tidyverse)

# Load the dplyr package
library(dplyr)

# Look at the gapminder dataset
gapminder
```

After we have installed the required package the dataset is tibble of dimensions 1704 $\times$ 6 with the attributes namely `country`, `continent`, `year`, `lifeExp`, `pop`, `gdpPercap`.

`lifeExp` reprsents the *life expectancy* of the individual country and `gdpPercap` represents the *GDP per capita* of a country.

Now as we proceed further with our initial steps of exploratory analysis it is customary to get accustomed with the dataset, rather than jump straight away to visualizations. Hence, by using  `arrange()`function we can get the countries with *least* and *highest* `lifExp`, `gdpPercap`.

- The country with the least life expectancy has been **Rwanda** in the year 1992.
- The country with the highest life expectancy has been **Japan** in the year 2007.
- The country with the least GDP per capita income is **Democratic Republic of Congo**  in the year 2007 with $241.16 billion.
- The country with the highest GDP per capita income is **Kuwait** with a massive amount of $113523.13 billion. This accounts to massive oil reserves in the country. We can also notice that **Kuwait** has almost remained in the first place for most of the years.

Now that we have seen a few observations let us visualize the correlations between the `lifeExp`,`pop`& the `gdpPercap` as the varying factor.

![A%20visual%20analysis%20of%20gapminder%20dataset%20f31775b310254dc89e19b51d803fca1c/output_33_0.png](A%20visual%20analysis%20of%20gapminder%20dataset%20f31775b310254dc89e19b51d803fca1c/output_33_0.png)

Figure 1: population vs. life expectancy

Notice that the x-axis goes from 1e5 (100,000) to 1e6 (1,000,000) to 1e7 (10,000,000) in equal increments.

Can you tell what is the GDP of your country from this graph?

Now we will create a graph showing all the country-level data from 1952 t0 2007, to understand how global statistics have changed overtime.

![A%20visual%20analysis%20of%20gapminder%20dataset%20f31775b310254dc89e19b51d803fca1c/output_39_0.png](A%20visual%20analysis%20of%20gapminder%20dataset%20f31775b310254dc89e19b51d803fca1c/output_39_0.png)

Figure 2: GDP per capita vs. Life Expectancy

The median life expectancy for all the countries across al years is 60.7 years. An interesting fact is that the median life expectancy across countries is generally going up over time, but maximum GDP per capita is not.

We can group by any variable in your dataset to create a summary. Rather than comparing across time, we might be interested in comparing among continents. We will want to do that within one year of the dataset.

| continent | medianLifeExp | maxGdpPercap |
|-----------|:-------------:|-------------:|
| Africa    |    40.5925    |     5487.106 |
| Americas  |    56.0740    |    14847.127 |
| Asia      |    48.2840    |   113523.133 |
| Europe    |    67.6500    |   17909.490  |
| Oceania   |    70.2950    |   12247.395  |

We can notice that the continent of Oceania had the highest life expectancy for the year 1957.

Now let us visualize the median life expectancy and median GDP per capita per continent over time. 

![A%20visual%20analysis%20of%20gapminder%20dataset%20f31775b310254dc89e19b51d803fca1c/output_57_0.png](A%20visual%20analysis%20of%20gapminder%20dataset%20f31775b310254dc89e19b51d803fca1c/output_57_0.png)

Figure 3: median Life expectancy over the years

![A%20visual%20analysis%20of%20gapminder%20dataset%20f31775b310254dc89e19b51d803fca1c/output_64_0.png](A%20visual%20analysis%20of%20gapminder%20dataset%20f31775b310254dc89e19b51d803fca1c/output_64_0.png)

Figure 4: median GDP per capita over time

It looks like the median life expectancy across the countries is increasing over time.

Now let us examine median GDP per capita over all the years across different continents.

![A%20visual%20analysis%20of%20gapminder%20dataset%20f31775b310254dc89e19b51d803fca1c/output_60_0.png](A%20visual%20analysis%20of%20gapminder%20dataset%20f31775b310254dc89e19b51d803fca1c/output_60_0.png)

Figure 5: median GDP per capita over the years for different continents

**Bar chart and Box plot** representations of GDP percapita for different continents

![A%20visual%20analysis%20of%20gapminder%20dataset%20f31775b310254dc89e19b51d803fca1c/output_67_0.png](A%20visual%20analysis%20of%20gapminder%20dataset%20f31775b310254dc89e19b51d803fca1c/output_67_0.png)

Figure 6: median GDP for every continent

![A%20visual%20analysis%20of%20gapminder%20dataset%20f31775b310254dc89e19b51d803fca1c/output_78_0.png](A%20visual%20analysis%20of%20gapminder%20dataset%20f31775b310254dc89e19b51d803fca1c/output_78_0.png)

Figure 7: boxplot for median GDP percapita 

A bar plot is useful for visualizing summary statistics, such as the median GDP in each continent.

A boxplot is useful for comparing a distribution of values across several groups. In the above box plot, we'll examine the distribution of GDP per capita by continent. Since GDP per capita varies across several orders of magnitude, we'll need to put the y-axis on a log scale.

Continents like Europe and Americas in General have high rate of GDP per capita whereas in contrast Africa has the lowest.

Oceania being exception has highest GDP per capita because it has only 2 countries.

We've created a plot where each bar represents one continent, showing the median GDP per capita for each. But the x-axis of the bar plot doesn't have to be the continent: we can instead create a bar plot where each bar represents a country. 

Thus the bar plot comparing the GDP per capita between the countries in Europe looks like:

![A%20visual%20analysis%20of%20gapminder%20dataset%20f31775b310254dc89e19b51d803fca1c/output_69_0.png](A%20visual%20analysis%20of%20gapminder%20dataset%20f31775b310254dc89e19b51d803fca1c/output_69_0.png)

Figure 8: GDP percapita among different countries in Europe.

## Conclusions and improvements

This project is just a basic exploratory data analysis of the dataset. The project can be further dealt with much complex analysis and if possible implementation of few machine learning algorithms.

## Authors

**[Sathwik Vadlamani](https://nikhilsathwik.me/)** - *initial work, documentation*
