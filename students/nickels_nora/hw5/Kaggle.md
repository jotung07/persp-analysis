HW\_5 Collaboration - Kaggle
================
Nora Nickels
11/13/2017

Assignment 5
============

Perspectives of Computational Analysis - Fall 2017
--------------------------------------------------

Collaboration
=============

Kaggle
------

### 1. Create an account with Kaggle.com and sign in.

Done.

### 2. Explore the Kaggle competitions page, which maintains a list of open call projects. Describe one that is of interest to you. What is the goal of the competition? What would you have to do to make a submission?

I am obsessed with real estate, exterior, and interior design. So naturally I am super interested in the Zillow competition. It is titled "Zillow Prize: Zillow's Home Value and Prediction (Zestimate)". And the tagline is the following: Can you improve the algorithm that changed the world of real estate?

I'll start by saying I waste SO much time on these types of real estate value and descriptive sites. Zillow, Trulia, Redfin ... they are so fascinating to me. And I often wonder how accurate "Zestimates" truly are. Zestimates are the estimated value of a property. In Zillow's description of their competition, they explain how Zillow's Zestimate works, and state, " The Zestimate was created to give consumers as much information as possible about homes and the housing market, marking the irst time cosnumers had access to the type of home value information at no cost". Dramatic, but pretty true - one had to work directly with a broker or agent to get fairly accurate information on real estate valuation from the MLS before internet real estate sites such as Zillow were available. Zillow's median margin or error has decreased to 5% since being released 11 years ago.

The goal of the competition is for Zillow to improve the accuracy of the Zestimate even further by having participant submit a developed algorithm that makes predictions about the future sale prices of homes.

In order to make a submssion, an individual or team on Kaggle must participant in two rounds: the qualifying round and the final round. For the qualifying round, teams must build a home valuation algorithm using external data sources to engineer a model that improves the Zestimate residual error. The submission is evaluated on Mean Absolute Error between the predicted log errir and the actual log error, and there is a transactions training data that records this. This first round algorithm due date has actually already passed, and they'll announce the 100 top qualifying teams in January. Those teams then participate in the final round, which opens in February. These team must build a home valuation algorithm from scratch by using external data sources to help engineer new features. Then, and I think this is the coolest part, after these are due, Zillow uses a three-month sales tracking period where the predictions are evluated against the actual sale prices of homes. Real estate transaction data is public information, so this is why I think this competition is especially neat. To be one of the three winners in the second round, the team's model must beat a Zillow benchmark model when it is trainined on the same competition data when making predictions on sales during the sales tracking period.

Although by no means an expert in real estate valuation, I would take into consideration the following when creating my model. I would use the existing datasets provided to do thorough data visualization looking at the most important varibles that affect property value; I assume these would include a range of more tangible factors such as square footage, bedrooms, bathrooms, etc., but also crucial variables such as nearby businesses, valuation trends of homes of proximate distance, etc. I would recruit anyone I know in real estate for advice on this - especially because this market changes so frequently, I would want outside knowledge on top of the existing datasets. I would also want to include in my model a factor that takes into account the risk of purchase; often times there is property information that simply cannot be obtained until purchase, and I would need to take this into account. I would test models on the existing datasets, but would also start my appoximations early enough in the competition process that I could test it on my own "sales tracking period"" before submission.

I feel like a competition like this in real estate does play on the strengths of open calls. Real estate, unlike a platform such as Netflix, is based on a non-digital domain. That is, real estate properties are not digital properties, and so many factors that play into real estate valuation are constantly changing. Demand and utility fluctuates constantly, as does the market. Property values change with factors that range on a spectrum of predictability, including something as abstract as exterior and interior design trendiness.

### 3. Explore the available datasets on the Kaggle datasets page. Download one of the datasets and generate a descriptive plot that highlights some instructive characteristic of the data. Make sure your plot has a title, labeled axes and axis titles, and a legend if necessary. Submit your script (.R or py) and your plot (saved as a PDF). Make sure your script is properly commented and reproducible.

I downloaded a dataset that contains a list of finishers of the Boston Marathon from 2017. I ran the Chicago marathon for the second time this year and it's a secret goal of mine to qualify for Boston one day (secret to my family but clearly not a secret to you guys). Anyway the Boston Marathon the the only marathon in the US other than olympic trials that must of the participant have to qualify to participat.

The dataset contains name, age, gender, city and state, times at 9 different stages of the race, expected time, finish time, finish pace, overall place, gender place, and division place.

For my informative plot, I decided to create a "pyramid plot" that shows the counts of runners by gender and by age. I wanted to see if between male and female runners, a similar age distribution of qualifying runners exists.

``` r
library(tidyverse)
```

    ## Loading tidyverse: ggplot2
    ## Loading tidyverse: tibble
    ## Loading tidyverse: tidyr
    ## Loading tidyverse: readr
    ## Loading tidyverse: purrr
    ## Loading tidyverse: dplyr

    ## Warning: package 'ggplot2' was built under R version 3.3.2

    ## Conflicts with tidy packages ----------------------------------------------

    ## filter(): dplyr, stats
    ## lag():    dplyr, stats

``` r
set.seed(1234)

BostonMarathon <- read.csv("marathon_results_2017.csv")

plot <- ggplot(data = BostonMarathon, aes(x = Age, fill = M.F)) + 
  geom_bar(data = subset(BostonMarathon, M.F == "F")) + 
  geom_bar(data = subset(BostonMarathon, M.F == "M"), 
           mapping = aes(y = - ..count..),
           position = "identity") +
  scale_y_continuous(breaks = seq(-700, 700, 100), labels = abs(seq(-700, 700, 100))) +
  scale_x_continuous(breaks = seq(0, 100, 10), labels = abs(seq(0, 100, 10))) +
  coord_flip() +
  labs(title = "Boston Marathon 2017: Runner Gender and Age Breakdown",
       x = "Age",
       y = "Number of Runners") +
  scale_fill_discrete(name = "Gender")

plot
```

![](Kaggle_files/figure-markdown_github/plot-1.png)

``` r
ggsave("plot.pdf")
```

    ## Saving 7 x 5 in image

As you can see from the pyramid bar plot, the distributions are generally similar by gender. You can tell that more male runners qualify to run Boston, and there is a slight skew in that it seems like more women in their twenties run the marathon than man in their twenties, and more men in their forties, fifties, and sixties run the marathon than women in these age groups. Based on my personal race running experiences, this does seem to be the case. I probably spent far too much time creating this plot. Thank the lord for those R Studio cheat sheets that we got in CFSS.
