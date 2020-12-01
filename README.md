# Astronaut_Flight_Records_Reshaping_ListLike_Data

We often encounter messy list-like or string data that needs to be reshaped into separate rows for futher analysis, including genres, reviews, products, names, etc. Today, we'll walk through reshaping and cleaning up list-like data. We'll work with astronaut flight records from the CSIS International Astronaut Database (https://aerospace.csis.org/data/international-astronaut-database/) in which "astronaut" is defined as someone who has flown to an altitude of 100km or higher. The 'Flights' column includes a string of spacecraft for each astronaut.

Before reshaping, we couldn't help but do some high-level exploration of the original data. We discovered that:

    568 people, including 504 men and 64 women, from 42 countries have gone to space
    Humans have spent a total of 55918 days, 7005 hours, and 16323 minutes in space
    Gennady Padalka from Russia has spent the most amount of time in space at 878 days, 11 hours, and 29 minutes

We've also created dataframes for all women who've gone to space and number of astronauts by country. There's alot more we could dig into like flights and country trends over time, but let's focus on reshaping.

To reshape list-like data into separate rows, we'll set .assign() to values of split strings to 'Flights' column and apply .explode(). We'll create new Spacecraft and Year columns, splitting original messy 'Flights' string and set expand argument to True to create new columns. We'll then clean up and set the dataframe to the format we want. The purpose is to reshape list-like data into a dataframe focused on individual astronauts with each spacecraft in which they traveled.
