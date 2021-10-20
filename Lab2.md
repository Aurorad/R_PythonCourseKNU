## 1. Creates a vector v of 100 elements with the command v <- rnorm (100). For this vector, print: the 10th element; elements from the 10th to the 20th inclusive; 10 elements starting from the 20th; items greater than 0.
a <- rnorm(100)
print(a)
print(a[10])

for (i in 10:20) {
  print(a[i])
}

i <- 20
while (i < 20 + 10) {
  print(a[i])
  i <- i + 1
}

for (j in 1:100){
  if (a[j] > 0) {
    print(a[j])
  }
}

## 2. Create a frame (data frame) y with the command y <- data.frame (a = rnorm (100), b = 1: 100, cc = sample (letters, 100, replace = TRUE)). To do this, print the data frame: the last 10 lines; terms from 10 to 20 inclusive; 10th element of column b; full column cc, using the column name.
y <- data.frame(a = rnorm(100), b = 1:100, cc = sample(letters, 100, replace = TRUE))
y[90:100, 1:3]
y[10:20, 1:3]
y[10, 2]
y[1:100, "cc"]

## 3. Create a vector z with elements 1, 2, 3, NA, 4, NA, 5, NA. For this vector: output all elements that are not NA; calculate the average of all elements of this vector without NA values and with NA values.
z <- c(1, 2, 3, NA, 4, NA, 5, NA)
for (i in 1:8) {
  if (!is.na(z[i])) {
    print(z[i])
  }
}
print(mean(z))
print(mean(z, na.rm=TRUE))
