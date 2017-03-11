# AzaveaTest
Data analysis test for Azavea

## Part 1: Conceptual Question
**(a)** A dataset contains data for 350 manufacturing companies in Europe. The following variables are included in the data for each company: industry, number of employees, salary of the CEO, and total profit. **We are interested in learning which variables impact the CEO's salary.**

    *test response*
  
**(b)** A market research company is hired to help a startup analyze their new product. **We want to know whether the product will be a success or failure.** Similar products exist on the market so the market research company gathers data on 31 similar products. The company records the following data points about each previously launched product: price of the product, competition price, marketing budget, ten other variables, and whether or not it succeeded or failed.

**(c)** Every week data is collected for the world stock market in 2012. The data points collected include the % change in the dollar, the % change in the market in the United States, the % change in the market in China, and the % change in the market in France. **We are interested in predicting the % change in the dollar in relation to the changes every week in the world stock markets.**


## Part 2: Applied Question

(a) Create a binary variable that represents whether the car's mpg is above or below its median. Above the median should be represented as 1. Name this variable mpg_binary.

```{r}
# Read read mileage data into new data frame
df = read.csv("Cars_mileage.csv", header = T, sep = ",")

# Add variable for median mileage
df$binary_median = NA

# Apply binary classification
df$binary_median = sapply(1:length(df$mpg), function(x){
  
  if(df$mpg[x] >= median(df$mpg)){
    return(1)
    
  } else {
    
    return(0)
  }
  
})
```


#### (b) Which of the other variables seem most likely to be useful in predicting whether a car's mpg is above or below its median? Describe your findings and submit visual representations of the relationship between mpg_binary and other variables.



