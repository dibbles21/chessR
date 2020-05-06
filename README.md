
# chessR

<!-- badges: start -->

[![Travis build
status](https://travis-ci.org/JaseZiv/chessR.svg?branch=master)](https://travis-ci.org/JaseZiv/chessR)
<!-- badges: end -->

## Overview

This package is designed to allow users to extract their game data from
the popular online chess platform [chess.com](https://www.chess.com/).

The website offers a very convenient set of APIs to be able to access
and documentation to these can be found
[here](https://www.chess.com/news/view/published-data-api).

## Installation

You can install the chessR package from github with:

``` r
# install.packages("devtools")
devtools::install_github("JaseZiv/chessR")
```

## Usage

The functions available in this package are designed to enable the
extraction of chess game data.

### Data Extraction

The functions detailed below relate to extracting data from chess.com

**Raw Game Data**

The `get_raw_game_data()` function can take either a single, or multiple
usernames. It will output a data frame with all the games played by that
user.

``` r
# install.packages("devtools")
raw_chess <- get_raw_chessdotcom("JaseZiv")
```

**Analysis Data**

The following function will extract the same data that the
`get_raw_chessdotcom()` function will, however this function will also
include additional columns to make analysing data easier.

The function can be used either on a single player, or a character
vector of multiple players.

``` r
chess_analysis_single <- get_game_data("JaseZiv")

chess_analysis_multiple <- get_game_data(c("JaseZiv", "elroch"))
```

**Get Top Players’ usernames**

The below function allows the user to extract the top 50 leaders on the
chess.com leaderboards for a number of different game types.

The game types include:

> *“daily”, “daily960”, “live\_rapid”, “live\_blitz”, “live\_bullet”,
> “live\_bughouse”, “live\_blitz960”, “live\_threecheck”,
> “live\_crazyhouse”, “live\_kingofthehill”, “lessons” and “tactics”*.

The usernames that are contained in the results can then be passed to
`get_raw_chessdotcom()` outlined above.

``` r
daily_leaders <- chessdotcom_leaderboard(game_type = "daily")
```

For a detailed guide to using the package and the functions for
analysis, see the package
[vignette](https://jaseziv.github.io/chessR/articles/using_chessR_package.html)
