Divvy Tripdata Database
================

## Introduction

## Divvy Database Creation

### Database connection

Establish postgresql database connection

``` r
# Read config
config <- read.ini("resources/db_config.ini")
db <- config$postgresql

# Safe database connection
tryCatch({
  con <- dbConnect(
    Postgres(),
    host = db$host,
    dbname = db$database,
    user = db$user,
    password = db$password,
    port = as.integer(db$port)
  )
}, error = function(e) {
  stop("Database connection failed: ", e$message)
})

knitr::opts_chunk$set(connection = con)
```

### Database schema

Create database schema to the database

``` sql
CREATE SCHEMA IF NOT EXISTS divvy;
```

### Databse tables

### Database views

### Database functions

## Exploratory Data Analysis

## Conclusion
