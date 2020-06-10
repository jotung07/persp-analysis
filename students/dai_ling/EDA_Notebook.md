EDA Analysis Notebook
================

Part 1: EDA on Distributions (Single Variable)
----------------------------------------------

``` r
#c(educ, degree, polviews, income06, happy)

for (i in ordinal) {
  barplot(table(gss[i]))
}
```

![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Bar%20Plots%20for%20Selected%20Ordinal%20Variables-1.png)![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Bar%20Plots%20for%20Selected%20Ordinal%20Variables-2.png)![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Bar%20Plots%20for%20Selected%20Ordinal%20Variables-3.png)![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Bar%20Plots%20for%20Selected%20Ordinal%20Variables-4.png)![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Bar%20Plots%20for%20Selected%20Ordinal%20Variables-5.png) Results:

1.  Education & Degree: For education level/degree, the data seems to have a bimodal distribution, with the highest mode at 12th grade and the second highest mode at 4yrs of college education. This is in accordance with the distribution of "highest degree obtained". We can further test if the bimodal distribution is caused by stacked distributions of different groups (such as sex or race).

2.  Political views: most people identified themselves as moderate, and least people identified themselves as extremely libral/conservative.

3.  Income: The distribution of income level seems to have a mode at around $70,000 to $90,000. However, there is a possibility that the distribution is actually bimodal, becuase the number of respondents with income level "$50,000 to $59,999" is significantly lower than the number of respondents that fall into its neighbor bins.

4.  Happiness: Most respodents reported feeling "pretty happy". Relatively few people reported themselves as "not too happy".

``` r
#c(wrkstat, wrkgvt, marital, sex, race, region, religion)

for (i in nominal) {
  barplot(table(gss[i]), ylab = "Count", las=2)
}
```

![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Bar%20Plots%20for%20Selected%20Nominal%20Variables-1.png)![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Bar%20Plots%20for%20Selected%20Nominal%20Variables-2.png)![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Bar%20Plots%20for%20Selected%20Nominal%20Variables-3.png)![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Bar%20Plots%20for%20Selected%20Nominal%20Variables-4.png)![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Bar%20Plots%20for%20Selected%20Nominal%20Variables-5.png)![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Bar%20Plots%20for%20Selected%20Nominal%20Variables-6.png)![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Bar%20Plots%20for%20Selected%20Nominal%20Variables-7.png)

Results:

1.  Work Status: A significant proportion of the respondents fall into the category of full-time workers.

2.  Work Type (government vs private): Among the working respondents, there are significantly more people who work for private companies than those who work for the government.

3.  Marital Status: The male:female ratio of respondents in the sample is not 50:50. Instead, there are considerably more female respondents in the sample than male respondents. (Why is it the case? Is it caused by the sampling method? Or do males have a lower respondence rate as compared to females?)

4.  Sex: There are noticieably more females than males in the sample.

5.  Race: The sample is dominated by white respondents.

6.  Region

7.  Religion

``` r
#c(sibs, childs, age, eqwlth, size)

for (i in discrete) {
  hist(gss[[i]], main = colnames(gss)[i],
       xlab = colnames(gss)[i])
}
```

![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Histogram%20for%20selected%20Discrete%20Variables-1.png)![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Histogram%20for%20selected%20Discrete%20Variables-2.png)![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Histogram%20for%20selected%20Discrete%20Variables-3.png)![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Histogram%20for%20selected%20Discrete%20Variables-4.png)![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Histogram%20for%20selected%20Discrete%20Variables-5.png)

### Part 2: Cross-analysis of variables

``` r
#income06 vs race
ggplot(data = gss) +
  geom_bar(
    mapping = aes(x = income06,fill = race),
    position = "fill"
  ) + theme(axis.text.x = element_text(angle = 90, hjust = 1))
```

![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Stacked%20Bar%20Plots-1.png)

``` r
#income06 vs sex
ggplot(data = gss) +
  geom_bar(
    mapping = aes(x = income06,fill = sex),
    position = "fill"
  ) + theme(axis.text.x = element_text(angle = 90, hjust = 1))
```

![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Stacked%20Bar%20Plots-2.png)

``` r
#income06 vs degree
ggplot(data = na.omit(gss[,c(11,18)])) +
  geom_bar(
    mapping = aes(x = income06,fill = degree),
    position = "fill"
  ) + theme(axis.text.x = element_text(angle = 90, hjust = 1))
```

![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Stacked%20Bar%20Plots-3.png)

``` r
#income06 vs happy
ggplot(data = na.omit(gss[,c(18,76)])) +
  geom_bar(
    mapping = aes(x = income06,fill = happy),
    position = "fill"
  ) + theme(axis.text.x = element_text(angle = 90, hjust = 1))
```

![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Stacked%20Bar%20Plots-4.png)

``` r
#income06 vs polviews
ggplot(data = na.omit(gss[,c(14,18)])) +
  geom_bar(
    mapping = aes(x = income06,fill = polviews),
    position = "fill"
  ) + theme(axis.text.x = element_text(angle = 90, hjust = 1))
```

![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Stacked%20Bar%20Plots-5.png)

``` r
#degree vs sex
ggplot(data = gss) +
  geom_bar(
    mapping = aes(x = degree,fill = sex),
    position = "fill"
  ) + theme(axis.text.x = element_text(angle = 90, hjust = 1))
```

![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Stacked%20Bar%20Plots-6.png)

``` r
#degree vs race
ggplot(data = gss) +
  geom_bar(
    mapping = aes(x = degree,fill = race),
    position = "fill"
  ) + theme(axis.text.x = element_text(angle = 90, hjust = 1))
```

![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Stacked%20Bar%20Plots-7.png) (1) Income vs Race: From the stacked bar plot, we can observe that the high income groups are dominanted by white people. Overall, the proportion of white people increases and that of the black people decreases steadily as the income level increases.

1.  Income vs Sex: No obvious trend from the chart. The gender ratio remains relatively constant cross all income levels.

2.  Income vs Degree: From the bar plot, we can observe that the proportion of people with a bachelor or graduate degree increases dramatically, white the that of people with a degree lower than High School decreases dramatically. Overall, we can observe that there is a positive association between the income level and the highest level of education obtained.

3.  Income vs Happiness: The bar plot suggests a positive association between happiness and income level. Generally, people with higher income tend to feel happier.

4.  Income vs Political Views: No obvious pattern observable from the plot.

5.  Degree vs Sex: No obvious trend. The gender ratio remains relatively constant across all levels of educational degrees.

6.  Degree vs Race: From the bar plot, we can observe that the proportion of White people increases slightly and the that of black people decreases slightly as the degree level goes higher. However, the change across different levels of education is relatively small.

``` r
plot(jitter(gss$childs) ~ jitter(gss$sibs))
abline(lm(gss$childs~ gss$sibs), col="red")
```

![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Scatter%20plot-1.png)

``` r
plot(gss$size~jitter(gss$age)) #does not work!
```

![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Scatter%20plot-2.png)

``` r
plot(jitter(gss$childs)~jitter(gss$age))
```

![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Scatter%20plot-3.png)

``` r
plot(jitter(gss$eqwlth)~jitter(gss$age))
```

![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Scatter%20plot-4.png)

``` r
plot(jitter(gss$sibs)~jitter(gss$age))
```

![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Scatter%20plot-5.png) (1) Childs vs Sibs: No obvious pattern observable from the jittered scatter plot. However, the fitted linear regression line suggests that there might be a positive association between number of siblings and number of children.

### Part 3: Analysis of Views on Public Policies

``` r
#Boxplot (Eqlwlth ~ Polviews)
boxplot(eqwlth ~ polviews, data = gss)
```

![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Support%20of%20Policies%20by%20Group%20(Degree/Poliview)-1.png)

``` r
# According to the boxplot, we can observe that conservativists tend to support equal wealth
# while liberalists oppose equal wealth.

#Mosaic plot (Natspac)
plot(natspac ~ degree, data = gss) #trend
```

![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Support%20of%20Policies%20by%20Group%20(Degree/Poliview)-2.png)

``` r
plot(natspac ~ polviews, data = gss)
```

![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Support%20of%20Policies%20by%20Group%20(Degree/Poliview)-3.png)

``` r
#People with higher levels of degrees tend to agree that the national spend on space exploration should
#be increased, whereas peopel with lower degree levels tend to think that the spending is too much.

#Mosaic plot (Natenvir)
plot(natenvir ~ degree, data = gss)
```

![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Support%20of%20Policies%20by%20Group%20(Degree/Poliview)-4.png)

``` r
plot(natenvir ~ polviews, data = gss) #trend
```

![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Support%20of%20Policies%20by%20Group%20(Degree/Poliview)-5.png)

``` r
#NATHEAL
plot(natheal ~ degree, data = gss)
```

![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Support%20of%20Policies%20by%20Group%20(Degree/Poliview)-6.png)

``` r
plot(natheal ~ polviews, data = gss) #trend
```

![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Support%20of%20Policies%20by%20Group%20(Degree/Poliview)-7.png)

``` r
#natcity
plot(natcity ~ degree, data = gss)
```

![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Support%20of%20Policies%20by%20Group%20(Degree/Poliview)-8.png)

``` r
plot(natcity ~ polviews, data = gss) #trend
```

![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Support%20of%20Policies%20by%20Group%20(Degree/Poliview)-9.png)

``` r
#natcrime
plot(natcrime ~ degree, data = gss) #trend?
```

![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Support%20of%20Policies%20by%20Group%20(Degree/Poliview)-10.png)

``` r
plot(natcrime ~ polviews, data = gss)
```

![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Support%20of%20Policies%20by%20Group%20(Degree/Poliview)-11.png)

``` r
#natdrug
plot(natdrug ~ degree, data = gss)
```

![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Support%20of%20Policies%20by%20Group%20(Degree/Poliview)-12.png)

``` r
plot(natdrug ~ polviews, data = gss) #trend
```

![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Support%20of%20Policies%20by%20Group%20(Degree/Poliview)-13.png)

``` r
#nateduc
plot(nateduc ~ degree, data = gss)
```

![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Support%20of%20Policies%20by%20Group%20(Degree/Poliview)-14.png)

``` r
plot(nateduc ~ polviews, data = gss)#trend
```

![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Support%20of%20Policies%20by%20Group%20(Degree/Poliview)-15.png)

``` r
ggplot(data = na.omit(gss[,c(30,10)])) +
  geom_bar(
    mapping = aes(x = educ, fill = nateduc),
    position = "fill"
  ) + theme(axis.text.x = element_text(angle = 90, hjust = 1))
```

![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Support%20of%20Policies%20by%20Group%20(Degree/Poliview)-16.png)

``` r
#Generally, we can observe that people with higher education are more likely to think the
#national spending on education is too little.


#natrace
plot(natrace ~ degree, data = gss)
```

![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Support%20of%20Policies%20by%20Group%20(Degree/Poliview)-17.png)

``` r
plot(natrace ~ polviews, data = gss) #trend
```

![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Support%20of%20Policies%20by%20Group%20(Degree/Poliview)-18.png)

``` r
plot(natrace ~ race, data = gss) #specific case
```

![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Support%20of%20Policies%20by%20Group%20(Degree/Poliview)-19.png)

``` r
#natarms
plot(natarms ~ degree, data = gss) #trend
```

![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Support%20of%20Policies%20by%20Group%20(Degree/Poliview)-20.png)

``` r
plot(natarms ~ polviews, data = gss) #trend
```

![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Support%20of%20Policies%20by%20Group%20(Degree/Poliview)-21.png)

``` r
#nataid
plot(nataid ~ degree, data = gss)
```

![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Support%20of%20Policies%20by%20Group%20(Degree/Poliview)-22.png)

``` r
plot(nataid ~ polviews, data = gss) #trend
```

![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Support%20of%20Policies%20by%20Group%20(Degree/Poliview)-23.png)

``` r
#
plot(natfare ~ degree, data = gss) #trend?
```

![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Support%20of%20Policies%20by%20Group%20(Degree/Poliview)-24.png)

``` r
plot(natfare ~ polviews, data = gss) #trend
```

![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Support%20of%20Policies%20by%20Group%20(Degree/Poliview)-25.png)

``` r
#natsoc
plot(natsci ~ degree, data = gss) #trend
```

![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Support%20of%20Policies%20by%20Group%20(Degree/Poliview)-26.png)

``` r
plot(natsci ~ polviews, data = gss)
```

![](EDA_Notebook_files/figure-markdown_github-ascii_identifiers/Support%20of%20Policies%20by%20Group%20(Degree/Poliview)-27.png)
