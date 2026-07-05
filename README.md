# DATA 612 Project 5 — Recommender System on Spark

Adapts the matrix factorization recommender from Project 3 to run on Apache
Spark using sparklyr in R.

## What this does

Project 3 built SVD and SGD recommenders in plain R, subsampled to 1,000 users
to run in memory. This project runs the same idea on Spark's built-in ALS model,
trained on the full MovieLens 10M dataset with no subsampling.

## Results

| Method | Data | RMSE |
|---|---|---|
| Project 3: Classic SVD | 1K users, subsampled | 0.972 |
| Project 3: SGD-SVD | 1K users, subsampled | 0.989 |
| Project 5: Spark ALS | Full 10M ratings | 0.819 |

Spark trained on all 10 million ratings and got a lower RMSE. More data, better
predictions — something base R could not do without shrinking the dataset first.

## Files

- `Project5_Spark.Rmd` — the R Markdown source
- `Project5_Spark.html` — knitted output

## Running it

Requires Java 17, sparklyr, and Spark 3.5.

```r
install.packages("sparklyr")
sparklyr::spark_install(version = "3.5")
```

The data downloads automatically on first knit.

## Links

- rpubs: https://rpubs.com/mark_data/spark
