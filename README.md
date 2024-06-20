# Le-Wagon-Case-Study
Case study for Le Wagon DS bootcamp.


# Notes
## Data

TARGETS (default) ARE NOT BALANCED (SMOTE? stratify the train/test split)

DISTRIBUTIONS OF MANY COLS ARE NOT NORMAL


The data is essentially JUNK...haha.
There are a lot of columns, 43 in total and many of them have a lot of NA values
(see Preprocessing for details). I dropped the columns that have more than 50%
of their values as NA.

A number of columns are heavily correlated. Anything with a correlation > .8
was dropped.

Further, many numerical columns are highly distributed and have a large
number of outliers.


## Preprocessing
I test with and without drop_duplicates() and dropna() prior to starting the
pipeline. Both times, I got the same prediction resuts: 0.074
Note that this is without any special feature selection and only basic
preprocessing in the pipeline (scaling & encoding).

However, doing these two drops, cut the number of rows from 89,976 rows (afer
removing the entries with 'default' == NA since this is what we want to predict)
to 9,111 rows. The original dataset has 99,976 rows. All of the rows that
are removed are in the dropna() portion, there don't seem to be any duplicates.
