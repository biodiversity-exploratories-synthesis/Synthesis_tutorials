Quality checks in big datasets
================
N. V. Schenk
2023-06-15

## Aim

This is a collection of quality checks which can be used for big
datasets, as e.g. for synthesis datset assembly.

## Quality checks in R

Basic testing can be done by checking the number of rows etc. by hand in
the console. Written tests are to be preferred because those tests are
reproducible. Ideally include the expected value either as comment or as
test, as shown in the example below:

Compare observed vs. expected

``` r
nrow(iris) == 150 # if observed == expected : T, if unexpected : FALSE
```

    ## [1] TRUE

Use automated tests as implemented in RStudio

## Quality checks

- after each data wrangling step, check carefully if the number of below
  items corresponds to the expected number :
  - number of plots
  - number of NA values
- column class (character, numeric, factor). Check if class is as
  expected.
  - character : only for comments (long text)
  - factor : categories of measurements, plot names. Try to use factors
    wherever possible and avoid characters.
  - numeric : all kinds of numbers
- factors (categorical variables) :
  - check levels
- correlations :
  - assembled variables are (often) correlated with the raw variables
  - indicators of the same process in different years correlated?
- duplicates : use `unique()` and `duplicated()` functions
- non-finite values : check if any present
- correct, document and feedback any errors found in used material –\>
  let creators correct errors in the original version.

## Synthesis datasets

- number of plots \>= 100
- select plots : grasslands (AEG) and/ or forests (AEF)
- check plot encoding : the two most often used versions of plot names
  are : “AEG1” (official name) and “AEG01” (often used)
  - The “AEG01” is an often used alternative because it allows better
    sorting in Excel (AEG01, AEG02, .. versus AEG1, AEG11, …)
- before aggregating values from several vectors :
  - check outliers –\> biologically possible outlier or typo?
- missing plots :
  - sometimes, an aggregated value is calculated of two vectors x and y,
    e.g. the mean of two pH measures. If a plot is missing in only one
    of two vectors x and y, use the value of the non-missing vector to
    compute the aggregated value.
  - missing vs. zeros. Sometimes, missing values are reported as zeros.
    Evaluate if the NA and 0 values are reported correctly : missing
    (NA) values are true missing values (intented to measure, but
    measurement was not possible), where zeroes (0) are value which were
    measured, and the measurement result was zero (e.g. counted number
    of butterfly species, but no butterflies were there)
  - **missing species** : a species can be completely missing from a
    plot –\> keep in mind (and check with number of plots)
- Versions : always indicate the version of the BExIS dataset you are
  working with (if the original name of the data folder is kept
  (recommended), the version is visible from the name)
- years : check if all plots are present in all years –\> if checking
  the number of plots, check per year separately, because a missing plot
  in one of the years would not be detected

## Outlook

Collection of issues by Data Scientist meeting 2021. \[added in July\]