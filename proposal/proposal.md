Project proposal
================
Lauren, Maeve, Annika

``` r
library(tidyverse)
library(broom)
## Add any additional packages you are using here
```

## 1. Introduction

The introduction should introduce your general research question(s) and
your data (where it came from, how it was collected, what are the cases,
what are the variables, etc.).

The research question we’re exploring is…? In this project, we are using
data from the Football Datasets GitHub Repository. This dataset provides
detailed match statistics for all Bundesliga games in the 2024-2025
season that is taken from the Football Data UK Co website. Each row
represents a single match, with information on both the home and away
teams, goals scored, shot taken, scores throughout the game, fouls, etc.
See README for full variables and names.

Text goes here. Refer to the Markdown Quick Reference: Help -\> Markdown
Quick Reference.

## 2. Data

Text goes here. Place your data in the /data folder, and add dimensions
and codebook to the README in that folder. Then print out the output of
glimpse() or skim() of your data frame.

``` r
# Code goes here
# Read in your data file
# Print the output of glimpse() or skim()
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

Text goes here. - What variables will you visualize to explore your
research questions? - Will there be any other data that you need to find
to help with your research question? - Very preliminary exploratory data
analysis, including some summary statistics and visualizations, along
with some explanation on how they help you learn more about your data.
(You can add to these later as you work on your project.) - The data
visualization(s) that you believe will be useful in exploring your
question(s). (You can update these later as you work on your project.)

``` r
# Code goes here
# Code to calculate summary statistics
# Code for a visualization
#initial visualizations
```
