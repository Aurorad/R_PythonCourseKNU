## 1. Create variables of basic (atomic) types. Basic types: character, numeric, integer, complex, logical.
a0 <- "character"
a0
a1 <- 15.3
a1
a2 <- 3L
a2
a3 <- 2 + 3i
a3
a4 <- TRUE
a4

## 2. Create vectors that: contain a sequence from 5 to 75; contains the numbers 3.14, 2.71, 0, 13; 100 TRUE values.
b0 <- 5:75
b0
b1 <- c(3.14, 2.71, 0.13)
b1
b2 <- as.logical(1:101)
b2

## 3. Create the next matrix with matrix, and with cbind or rbind
col0 <- c(0.5, 3.9, 0, 2)
col1 <- c(1.3, 131, 2.2, 7)
col2 <- c(3.5, 2.8, 4.6, 5.1)
c <- cbind(col0, col1, col2)
c

## 4. Create an arbitrary list (list), which includes all basic types.
d <- list(a0, a1, a2, a3, a4)
d

## 5. Create a factor with three levels "baby", "child", "adult".
e <- factor(c("baby", "child", "adult", "child", "adult"),
  levels = c("baby", "child", "adult"))
e
table(e)

## 6. Find the index of the first value of NA in the vector 1, 2, 3, 4, NA, 6, 7, NA, 9, NA, 11. Find the number of NA values.
f <- c(1, 2, 3, 4, NA, 6, 7, NA, 9, NA, 11)
f
for (i in 1:11) {
  if (is.na(f[i])) {
    print(i)
    break
  }
}
counter <- 0
for (i in 1:11) {
  if (is.na(f[i])) {
    counter <- counter + 1
  }
}
print(counter)

## 7. Create an arbitrary data frame and display it in the console.
g <- data.frame(id = 1:3, name = c("Kate", "Tom", "John"), age = c(15, 17, 12))
g

## 8. Rename the columns of this data frame.
names(g)[1] <- "ID"
names(g)[2] <- "NAME"
names(g)[3] <- "AGE"
g

