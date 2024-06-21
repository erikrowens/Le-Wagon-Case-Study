# Le-Wagon-Case-Study
Case study for Le Wagon DS bootcamp.


# Notes
My submission for Le Wagon technical case study. Still need to fine tune the
model.

## Data
* The data is rather 'messy' with lots of NA...haha.
* Targets are not balanced
* There are a lot of columns, 43 in total and many of them have a lot of NA values
(see Preprocessing for details). I dropped the columns that have more than 30%
of their values as NA.
* A number of columns are heavily correlated. Anything with a correlation > .8
was dropped.
* urther, many numerical columns are highly distributed and have a large
number of outliers.


## Preprocessing
I test with and without drop_duplicates() and dropna() prior to starting the
pipeline. Both times, I got the same prediction resuts. Note that this is
without any special feature selection and only basic preprocessing in the
pipeline (scaling & encoding).

However, doing these two drops, cut the number of rows from 89,976 rows (afer
removing the entries with 'default' == NA since this is what we want to predict)
to 9,111 rows. The original dataset has 99,976 rows. All of the rows that
are removed are in the dropna() portion, there don't seem to be any duplicates.
