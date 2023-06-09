# Data-Cleaning-with-Python

## Project Goal:
The goal of this project is to showcase the data cleaning and wrangling process required to fit a GNN (Graph Neural Network) model using Python.

## Context:
The raw dataset used in this project was obtained from a survey conducted with vehicle customers. In accordance with confidentiality agreements, the actual data will not be displayed. Only the structured and indexed column names will be disclosed.

The raw dataset includes a record for each vehicle buyer, capturing customer information, details of the purchased car, and characteristics of both the purchased car and the car(s) considered before making the purchase.

It is important to note that the dataset records up to two cars that were considered by each customer, in addition to the car that they ultimately purchased:

| respondent id | purchased car | first considered car | second considered car | feature 1 of purchased car: price| feature 2 of purchased car: body type| ... |feature n of purchased car|
|---------------|---------------|----------------------|-----------------------|----------------------------------|--------------------------------------| --- | ------------------------ |
|  1  | Tesla Model 3  | Hyundai Ioniq 5  | N/A         | 40,240 | Sedan | ... | ...|
|  2  | Toyota Camry   | Hyundai Sonata   | Honda Civic | 26,320 | Sedan | ... | ...|


## Results:
To prepare the dataset for GNN modeling, the following two steps will be undertaken:

1. Create a Model List:
* This step involves recording the features of each car model.

2. Expand the Raw Dataset:
* In this step, the raw dataset will be expanded so that there is one row per customer and car model considered.
* Each record will include customer features and the features of the cars being recorded.
* Additionally, a purchase indicator will be included to indicate whether the car was purchased or not.

For example, the above dataset will finally be transformed to the following status:

| respondent id | car | purchased | feature 1: price | feature 2: body type | ... | feature n |
|---------------|-----|-----------|------------------| -------------------- | ----|---------- |
|  1  | Tesla Model 3    | 1  | 40,240 | Sedan | ... | ...|
|  1  | Hyundai Ioniq 5  | 0  | 41,450 | SUV   | ... | ...|
|  2  | Toyota Camry     | 1  | 26,320 | Sedan | ... | ...|
|  2  | Hyundai Sonata   | 0  | 25,250 | Sedan | ... | ...|
|  2  | Honda Civic      | 0  | 23,750 | Hatchback | ... | ...|

