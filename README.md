# ECE2112_PA3

Adele Mc Nicolai V. Agbayani | 2ECE-B

This repository contains Programming Assignment 3 for ECE2112: Advanced Computer Programming and Algorithms. This experiment introduces Python data analysis using Pandas through problems involving DataFrames, positional and label-based indexing, Boolean indexing, and data subsetting.

# Objective

The objective of this experiment is to apply the fundamental concepts of Pandas in selecting, filtering, and extracting data from a DataFrame.

# Discussion of the Experiment

The experiment contains three programming problems that apply different Pandas data selection techniques. Each problem uses the provided cars.csv dataset to retrieve specific rows and columns without modifying the original DataFrame.

# 1. Positional and Label-Based Slicing

The first problem involves selecting rows and columns from the cars DataFrame using positional and label-based indexing.

The .iloc[] indexer was used to select row 6 through 10 based on their positions:

cars_6_to_10 = cars.iloc[5:10]

Since Python uses zero-based indexing, position 5 corresponds to the sixth row of the dataset. The ending position in a slice is excluded, so 5:10 selects five rows corresponding to rows 6 through 10.

Column labels were then used to retain only the required columns:

cars_6_to_10[[”Model”, “mpg”, “cyl”, “hp”, “gear”,]]

This returns the specified columns in the given order.

# 2. Model Lookup

This second problem involves locating specific vehicles based on values in the Model column. Boolean indexing was used instead of hard-coded row numbers.

For example: 

toyota = cars[cars[”Model”] == “Toyota Corolla”]

The condition compares each value in the Model column with “Toyota Corolla”. Only the row where the condition is True is included in the resulting DataFrame.

The same method was used to locate the Pontiac Firebird, after which only the required columns were selected:

pontiac = cars[cars["Model"] == "Pontiac Firebird"]
pontiac = pontiac[["Model", "mpg", "hp", "wt"]]

# 3. Multi-Model Subsetting

The third problem involves creating a DataFrame containing three specific vehicle models while retaining only the required columns.

The .isin() method was used to check whether each value in the Model column belongs to the given list:

selected_cars = cars [
  cars[”Model”].isin([”Datsun 710”, “Lotus Europa”, “Ferrari Dino”])
  ]

The required columns were then selected using their labels:

selected_cars = selected_cars[[”Model”, “mpg”, “cyl”, “hp”, “gear”]]

The resulting DataFrame contains three rows and five columns, giving a shape of (3, 5) as required by the experiment.

# Conclusion

The experiment demonstrated different methods of selecting and filtering data using Pandas. Positional indexing with .iloc[], Boolean indexing, .isin(), and column-label selection were used to extract specific subsets from a DataFrame while keeping the original dataset.
