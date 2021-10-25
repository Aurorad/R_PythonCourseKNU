# LAB3
### 1. The add2 (x, y) function, which returns the sum of two numbers.
```
add2 <- function(x, y) {
  x + y
}
add2(1, 2
#[1] 3
```

### 2. A function above (x, n) that takes a vector and a number n and returns all elements of the vector that are greater than n. The default is n = 10.
```
above <- function (x, n = 10) {
  x[x > n]
}
c <- c(1, 5, 2, 6, 12, 322, 43)
above(c, 5)
#[1]   6  12 322  43
```

### 3. The function my_ifelse (x, exp, n), which takes the vector x, compares all its elements with exp with n, and returns the elements of the vector that correspond to the expression condition. For example, my_ifelse (x, ">", 0) returns all elements of x that are greater than 0. Exp can be equal to "<", ">", "<=", "> =", "==". If exp does not match any of these expressions, the vector x is returned.
```
my_ifelse <- function (x, exp, n) {
  if (exp == "<") {
    x[x < n]
  }
  else if (exp == ">") {
    x[x > n]
  }
  else if (exp == "<=") {
    x[x <= n]
  }
  else if (exp == ">=") {
    x[x >= n]
  }
  else if (exp == "==") {
    x[x == n]
  }
  else {
    x
  }
}

my_ifelse(c, "<", 5)
#[1] 1 2
my_ifelse(c, ">", 5)
#[1]   6  12 322  43
my_ifelse(c, "<=", 5)
#[1] 1 5 2
my_ifelse(c, ">=", 5)
#[1]   5   6  12 322  43
my_ifelse(c, "==", 5)
#[1] 5
```

### 4. The columnmean (x, removeNA) function, which calculates the mean value for each column of the matrix, or data frame. The removeNA logical parameter specifies whether to delete the NA value. By default, it is TRUE.
```
columnmean <- function (x, removeNA = TRUE) {
  colMeans(x, na.rm=removeNA)
}

m <- matrix (1:6, nrow=2, ncol=3)
columnmean(m)
#[1] 1.5 3.5 5.5
```
