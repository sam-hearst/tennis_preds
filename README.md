# Project Overview

## The Problem Area

Tennis is considered one of the most popular sports internationally. It has millions of followers and many people offering thoughts on who will or won't win a match. However predicting the winner of a tennis match is hard. There are so many variables that go into who will be victorious. There is the different surfaces of the court, the confidence of the player, and then just who seems to be playing well on the day.

## Data Science Solution

Given this problem, I am looking to build a machine learning model that can seek to answer it. I want to see if I can build a model that will predict the outcome of tennis matches on the ATP (men's) tour after 2000. I want to explore the variables that can function as best predictors and just as importantly explore the variables that we may think contribute, but in actuality don't.

Predicting the winner of any sporting event is difficult. Given this fact, I realize that my model will be fallible. Instead of looking for perfection, I would like to compare my model's successfulness against the most simple way to pick a winner in a tennis match: choosing whoever is ranked higher. 

Creating a using a model like this could have an impact in the world of sports betting. Thus, for my last part of the project I would like to explore how my model would fare if I were to it's predictions to place bets on those matches.  In the end I hope to build a model that can the simplest predictive method discussed above, and also see how it can compare to real bets on the outcomes of those matches. 

## Initial EDA (Exploratory Data Analysis)

For this project, I will be using JeffSackmann's tennis_atp repository, which has all ATP matches starting from 2000. The data provided is fairly clean. The general data information is as follows:

### Data Dictionary

* Many of the columns are self-explanatory, and so for those I may leave out a description. Other columns that I do not end up using or that were specific to JeffSackmann's repo I will omit.

tourney_id - a unique identifier for each tournament, such as 2020-888. The exact formats are borrowed from several different sources, so while the first four characters are always the year, the rest of the ID doesn't follow a predictable structure.

tourney_name - tournament name

surface - court surface

draw_size - number of players in the draw, often rounded up to the nearest power of 2. (For instance, a tournament with 28 players may be shown as 32.)

tourney_level - For men: 'G' = Grand Slams, 'M' = Masters 1000s, 'A' = other tour-level events, 'C' = Challengers, 'S' = Satellites/ITFs, 'F' = Tour finals and other season-ending events, and 'D' = Davis Cup 

tourney_date - eight digits, YYYYMMDD, tournaments usually start on Monday.

winner_seed

winner_entry - 'WC' = wild card, 'Q' = qualifier, 'LL' = lucky loser, 'PR' = protected ranking, 'ITF' = ITF entry, and there are a few others that are occasionally used.

winner_name

winner_hand - R = right, L = left, U = unknown. For ambidextrous players, this is their serving hand.

winner_ht - height in centimeters, where available

winner_ioc - three-character country code

winner_age - age, in years, as of the tourney_date

loser_id

loser_seed

loser_entry

loser_name

loser_hand

loser_ht

loser_ioc

loser_age

score

best_of - '3' or '5', indicating the the number of sets for this match

round

minutes - match length, where available

w_ace - winner's number of aces
w_df - winner's number of doubles faults
w_svpt - winner's number of serve points
w_1stIn - winner's number of first serves made
w_1stWon - winner's number of first-serve points won
w_2ndWon - winner's number of second-serve points won
w_SvGms - winner's number of serve games
w_bpSaved - winner's number of break points saved
w_bpFaced - winner's number of break points faced

l_ace
l_df
l_svpt
l_1stIn
l_1stWon
l_2ndWon
l_SvGms
l_bpSaved
l_bpFaced

winner_rank - winner's ATP rank, as of the tourney_date, or the most recent ranking date before the tourney_date
winner_rank_points - number of ranking points, where available
loser_rank
loser_rank_points