# 1. Create a matrix with 5 columns and 10 rows using a matrix with random data (function rnorm (50)).
m1 <- matrix(rnorm(50), nrow = 10, ncol = 5)
m1

# 2. Find the maximum value in each column.
apply(m1,2,max)

# 3. Find the mean value of each column.
apply(m1,2,mean)

# 4. Find the minimum value in each line.
apply(m1,1,min)

# 5. Sort each column of the table.
apply(m1,2,sort)

# 6. Find the number of values <0 for each column. Use your feature.
colSums(m1 < 0)

# 7. Print a vector with Boolean values TRUE and FALSE. TRUE if there are elements> 2 in the column, FALSE if no.
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

# 8. Create a list list1 <- list (observationA = c (1: 5, 7: 3), observationB = matrix (1: 6, nrow = 2)). For this list, find sum using lapply.
list1 <- list(observationA = c(1:5, 7:3), observationB = matrix(1:6, nrow=2))
list1

lapply(list1,sum)

# 9. For each item in list1, find the maximum and minimum values (range) using lapply and sapply.
lapply(list1,range)

sapply(list1,range)

# 10. For the built-in InsectSprays dataset, find the average count for each spray.
aggregate(InsectSprays[, "count"], list(InsectSprays$spray), mean)

