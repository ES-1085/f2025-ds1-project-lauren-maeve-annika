Project proposal
================
Lauren, Maeve, Annika

``` r
library(tidyverse)
library(broom)
```

## 1. Introduction

The research question we’re exploring is how does being the home or away
team affect shots taken and shots on target?

In this project, we are using data from the Football Datasets GitHub
Repository. This dataset provides detailed match statistics for all
Bundesliga games in the 2024-2025 season that is taken from the Football
Data UK Co website. Each row represents a single match, with information
on both the home and away teams, goals scored, shot taken, scores
throughout the game, fouls, etc. See README for full variables and
names.

## 2. Data

``` r
# dim(season)
```

``` r
season <- read_csv("../data/season.csv")
```

    ## Rows: 306 Columns: 22
    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## chr  (5): Date, HomeTeam, AwayTeam, FTR, HTR
    ## dbl (16): FTHG, FTAG, HTHG, HTAG, HS, AS, HST, AST, HF, AF, HC, AC, HY, AY, ...
    ## lgl  (1): Referee
    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.

``` r
glimpse(season)
```

    ## Rows: 306
    ## Columns: 22
    ## $ Date     <chr> "23/08/24", "24/08/24", "24/08/24", "24/08/24", "24/08/24", "…
    ## $ HomeTeam <chr> "M'gladbach", "Augsburg", "Freiburg", "Hoffenheim", "Mainz", …
    ## $ AwayTeam <chr> "Leverkusen", "Werder Bremen", "Stuttgart", "Holstein Kiel", …
    ## $ FTHG     <dbl> 2, 2, 3, 3, 1, 1, 2, 2, 0, 1, 0, 3, 0, 3, 0, 2, 4, 2, 4, 2, 1…
    ## $ FTAG     <dbl> 3, 2, 1, 2, 1, 0, 0, 3, 2, 0, 2, 1, 2, 3, 0, 3, 0, 0, 2, 1, 4…
    ## $ FTR      <chr> "A", "D", "H", "H", "D", "H", "H", "A", "A", "H", "A", "H", "…
    ## $ HTHG     <dbl> 0, 2, 1, 2, 0, 0, 0, 0, 0, 1, 0, 2, 0, 2, 0, 2, 2, 1, 3, 0, 1…
    ## $ HTAG     <dbl> 2, 1, 1, 0, 0, 0, 0, 1, 0, 0, 0, 0, 2, 1, 0, 1, 0, 0, 1, 1, 2…
    ## $ HTR      <chr> "A", "H", "D", "H", "D", "D", "D", "A", "D", "H", "D", "H", "…
    ## $ Referee  <lgl> NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, N…
    ## $ HS       <dbl> 14, 10, 15, 20, 15, 12, 17, 11, 11, 10, 16, 17, 12, 28, 5, 27…
    ## $ AS       <dbl> 25, 12, 9, 15, 15, 10, 7, 14, 6, 8, 15, 10, 12, 9, 9, 10, 15,…
    ## $ HST      <dbl> 7, 3, 4, 8, 3, 3, 5, 2, 3, 5, 4, 7, 5, 13, 1, 10, 9, 4, 7, 9,…
    ## $ AST      <dbl> 9, 6, 2, 6, 4, 4, 2, 8, 3, 2, 6, 3, 4, 7, 4, 4, 1, 4, 4, 2, 8…
    ## $ HF       <dbl> 11, 11, 7, 8, 9, 9, 6, 13, 10, 10, 9, 10, 17, 6, 11, 7, 15, 1…
    ## $ AF       <dbl> 7, 10, 10, 14, 15, 17, 3, 11, 15, 11, 10, 10, 14, 12, 16, 8, …
    ## $ HC       <dbl> 2, 4, 6, 8, 8, 9, 7, 1, 4, 5, 3, 1, 1, 11, 5, 18, 5, 2, 8, 5,…
    ## $ AC       <dbl> 4, 2, 3, 6, 9, 3, 7, 7, 2, 4, 4, 4, 7, 2, 6, 2, 6, 4, 1, 6, 1…
    ## $ HY       <dbl> 1, 3, 2, 2, 1, 1, 0, 2, 2, 3, 1, 0, 4, 4, 2, 3, 0, 1, 2, 0, 2…
    ## $ AY       <dbl> 0, 1, 1, 3, 3, 3, 1, 3, 3, 1, 0, 3, 7, 2, 7, 1, 3, 0, 2, 3, 2…
    ## $ HR       <dbl> 0, 0, 0, 0, 0, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0…
    ## $ AR       <dbl> 0, 0, 0, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 0, 0, 0, 0, 0, 0…

## 3. Data analysis plan

- What variables will you visualize to explore your research questions?

We plan to use the HS, AS, HST, AST, HomeTeam, and AwayTeam variables to
visualize the question.

- Will there be any other data that you need to find to help with your
  research question?

No, as all of our data is in the existing dataset.

- Very preliminary exploratory data analysis, including some summary
  statistics and visualizations, along with some explanation on how they
  help you learn more about your data. (You can add to these later as
  you work on your project.)

The data visualization(s) that you believe will be useful in exploring
your question(s). (You can update these later as you work on your
project.)

- Histograms - to compare `HomeTeam` and `AwayTeam` depending on `HS`
  and `AS`

- Density plots - to compare `HS` and `AS` with `HST` and \`AST

- Scatter plot - comparing between the two teams

- Bar plots - to show a difference in `HS` and `AS`

``` r
# Code goes here
# Code to calculate summary statistics
season |>
  group_by(HomeTeam) |>
  summarise(
    mean_HS = mean(HS, na.rm = TRUE),
    mean_HST = mean(HST, na.rm = TRUE),
    sd_HS = sd(HS, na.rm = TRUE),
    sd_HST = sd(HST, na.rm = TRUE),
    r = cor(HS, HST, use = "complete.obs")
  )
```

    ## # A tibble: 18 × 6
    ##    HomeTeam      mean_HS mean_HST sd_HS sd_HST     r
    ##    <chr>           <dbl>    <dbl> <dbl>  <dbl> <dbl>
    ##  1 Augsburg         14.1     4.71  6.50   2.71 0.751
    ##  2 Bayern Munich    21.2     9     5.80   3.06 0.802
    ##  3 Bochum           14.5     4.41  4.52   2.21 0.647
    ##  4 Dortmund         15.3     5.41  5.34   2.12 0.783
    ##  5 Ein Frankfurt    16       5.82  6.57   2.13 0.711
    ##  6 Freiburg         12.4     4.47  5.16   2.60 0.825
    ##  7 Heidenheim       12.9     3.94  4.97   2.63 0.739
    ##  8 Hoffenheim       14.1     4.94  4.72   2.14 0.639
    ##  9 Holstein Kiel    11.2     4.24  4.67   2.59 0.633
    ## 10 Leverkusen       17.5     6.53  5.84   2.98 0.690
    ## 11 M'gladbach       12.6     4.71  4.05   2.62 0.698
    ## 12 Mainz            13.1     4.76  4.55   1.99 0.418
    ## 13 RB Leipzig       12.8     5.35  3.61   1.84 0.381
    ## 14 St Pauli         11.7     3.41  5.85   2.24 0.884
    ## 15 Stuttgart        16.2     6.35  6.49   3.02 0.694
    ## 16 Union Berlin     12.8     3.81  3.54   1.72 0.464
    ## 17 Werder Bremen    13.5     3.94  5.70   2.33 0.369
    ## 18 Wolfsburg        13.5     4.53  4.11   1.84 0.518

``` r
# Code for a visualization
#initial visualizations
```
