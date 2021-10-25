# LAB 1
### 1. Create variables of basic (atomic) types. Basic types: character, numeric, integer, complex, logical.
Character
```
a0 <- "character"
a0
#[1] "character"
```
Numeric
```
a1 <- 15.3
a1
#[1] 15.3
```
Integer
```
a2 <- 3L
a2
#[1] 3
```
Complex
```
a3 <- 2 + 3i
a3
#[1] 2+3i
```
Logic
```
a4 <- TRUE
a4
#[1] TRUE
```

### 2. Create vectors that: contain a sequence from 5 to 75; contains the numbers 3.14, 2.71, 0, 13; 100 TRUE values.
```
b0 <- 5:75
b0
#[1]  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30 31 32 33 34 35 36 37 38 39 40
#[37] 41 42 43 44 45 46 47 48 49 50 51 52 53 54 55 56 57 58 59 60 61 62 63 64 65 66 67 68 69 70 71 72 73 74 75
```
```
b1 <- c(3.14, 2.71, 0.13)
b1
#[1] 3.14 2.71 0.13
```
```
b2 <- as.logical(1:101)
b2
#[1] TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE
#[22] TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE
#[43] TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE
#[64] TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE
#[85] TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE
```

### 3. Create the next matrix with matrix, and with cbind or rbind
```
col0 <- c(0.5, 3.9, 0, 2)
col1 <- c(1.3, 131, 2.2, 7)
col2 <- c(3.5, 2.8, 4.6, 5.1)
c <- cbind(col0, col1, col2)
c
#     col0  col1 col2
#[1,]  0.5   1.3  3.5
#[2,]  3.9 131.0  2.8
#[3,]  0.0   2.2  4.6
#[4,]  2.0   7.0  5.1
```

### 4. Create an arbitrary list (list), which includes all basic types.
```
d <- list(a0, a1, a2, a3, a4)
d
#[[1]]
#[1] "character"

#[[2]]
#[1] 15.3

#[[3]]
#[1] 3

#[[4]]
#[1] 2+3i

#[[5]]
#[1] TRUE
```

### 5. Create a factor with three levels "baby", "child", "adult".
```
e <- factor(c("baby", "child", "adult", "child", "adult"),
  levels = c("baby", "child", "adult"))
e
#[1] baby  child adult child adult
#Levels: baby child adult
table(e)
#e
# baby child adult 
#    1     2     2 
```

### 6. Find the index of the first value of NA in the vector 1, 2, 3, 4, NA, 6, 7, NA, 9, NA, 11. Find the number of NA values.
```
f <- c(1, 2, 3, 4, NA, 6, 7, NA, 9, NA, 11)
f
#[1]  1  2  3  4 NA  6  7 NA  9 NA 11
for (i in 1:11) {
  if (is.na(f[i])) {
    print(i)
    break
  }
}
#[1] 5
counter <- 0
for (i in 1:11) {
  if (is.na(f[i])) {
    counter <- counter + 1
  }
}
print(counter)
#[1] 3
```

### 7. Create an arbitrary data frame and display it in the console.
```
g <- data.frame(id = 1:3, name = c("Kate", "Tom", "John"), age = c(15, 17, 12))
g
#  id name age
#1  1 Kate 15
#2  2 Tom  17
#3  3 John 12
```

### 8. Rename the columns of this data frame.
```
names(g)[1] <- "ID"
names(g)[2] <- "NAME"
names(g)[3] <- "AGE"
g
#  ID NAME AGE
#1  1 Kate  15
#2  2  Tom  17
#3  3 John  12
```
