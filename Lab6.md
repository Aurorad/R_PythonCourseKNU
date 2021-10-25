# LAB 6
### 1. Create a matrix with 5 columns and 10 rows using a matrix with random data (function rnorm (50)).
```
m1 <- matrix(rnorm(50), nrow = 10, ncol = 5)
m1
#          [,1]       [,2]        [,3]        [,4]       [,5]
# [1,] -0.9826622  0.4594098 -0.67351807 -1.24689702  0.5882758
# [2,] -1.3868206 -0.1736747 -1.42751280  1.99850790  0.6335603
# [3,] -1.4952723 -0.4388971  0.69325312  0.52092346 -1.4726649
# [4,] -0.3779543 -0.4565446 -0.81701189 -0.53702239  0.7322119
# [5,]  0.5229109 -0.9980328  0.87726810  0.29022172 -0.9002981
# [6,] -0.5841774  0.3555818  0.43374475 -0.54360755 -0.8961354
# [7,] -0.1674345 -1.8234386 -0.45959013 -0.07004936  0.1194667
# [8,] -2.1615383  0.5062946  0.55111415  1.60988763 -0.2265046
# [9,]  1.3246646  1.1525754  0.69318530  0.63654685  1.4980763
#[10,]  1.2913646 -0.3941528 -0.06078907  1.19931133 -1.3332459
```

### 2. Find the maximum value in each column.
```
apply(m1,2,max)
#[1] 1.3246646 1.1525754 0.8772681 1.9985079 1.4980763
```

### 3. Find the mean value of each column.
```
apply(m1,2,mean)
#[1] -0.40169194 -0.18108790 -0.01898566  0.38578226 -0.12572579
```

### 4. Find the minimum value in each line.
```
apply(m1,1,min)
#[1] -1.2468970 -1.4275128 -1.4952723 -0.8170119 -0.9980328 -0.8961354 -1.8234386 -2.1615383  0.6365469
#[10] -1.3332459
```

### 5. Sort each column of the table.
```
apply(m1,2,sort)
#            [,1]       [,2]        [,3]        [,4]       [,5]
# [1,] -2.1615383 -1.8234386 -1.42751280 -1.24689702 -1.4726649
# [2,] -1.4952723 -0.9980328 -0.81701189 -0.54360755 -1.3332459
# [3,] -1.3868206 -0.4565446 -0.67351807 -0.53702239 -0.9002981
# [4,] -0.9826622 -0.4388971 -0.45959013 -0.07004936 -0.8961354
# [5,] -0.5841774 -0.3941528 -0.06078907  0.29022172 -0.2265046
# [6,] -0.3779543 -0.1736747  0.43374475  0.52092346  0.1194667
# [7,] -0.1674345  0.3555818  0.55111415  0.63654685  0.5882758
# [8,]  0.5229109  0.4594098  0.69318530  1.19931133  0.6335603
# [9,]  1.2913646  0.5062946  0.69325312  1.60988763  0.7322119
#[10,]  1.3246646  1.1525754  0.87726810  1.99850790  1.4980763
```

### 6. Find the number of values <0 for each column. Use your feature.
```
colSums(m1 < 0)
#[1] 7 6 5 4 5
```

### 7. Print a vector with Boolean values TRUE and FALSE. TRUE if there are elements> 2 in the column, FALSE if no.
```
result <- c()
v <- colSums(m1 > 2)
for (i in v) {
  if (i > 0) {
    result <- c(result, TRUE)
  }
  else {
  result <- c(result, FALSE)
  }
}
result
#[1] FALSE FALSE FALSE FALSE FALSE
```

### 8. Create a list list1 <- list (observationA = c (1: 5, 7: 3), observationB = matrix (1: 6, nrow = 2)). For this list, find sum using lapply.
```
list1 <- list(observationA = c(1:5, 7:3), observationB = matrix(1:6, nrow=2))
list1

lapply(list1,sum)
#$observationA
# [1] 1 2 3 4 5 7 6 5 4 3

#$observationB
#     [,1] [,2] [,3]
#[1,]    1    3    5
#[2,]    2    4    6
```

### 9. For each item in list1, find the maximum and minimum values (range) using lapply and sapply.
```
lapply(list1,range)
#$observationA
#[1] 1 7

#$observationB
#[1] 1 6

sapply(list1,range)
#     observationA observationB
#[1,]            1            1
#[2,]            7            6
```

### 10. For the built-in InsectSprays dataset, find the average count for each spray.
```
aggregate(InsectSprays[, "count"], list(InsectSprays$spray), mean)
#  Group.1         x
#1       A 14.500000
#2       B 15.333333
#3       C  2.083333
#4       D  4.916667
#5       E  3.500000
#6       F 16.666667
```
