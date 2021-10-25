# LAB 4
```
data <- read.csv(file = "hw1_data.csv",  stringsAsFactors=FALSE)
```

### 1.What are the column names of the data file?
```
names(data)
#[1] "Ozone"   "Solar.R" "Wind"    "Temp"    "Month"   "Day"
```

### 2. Print the first 6 lines of the data frame.
```
data[1:6,]
#  Ozone Solar.R Wind Temp Month Day
#1    41     190  7.4   67     5   1
#2    36     118  8.0   72     5   2
#3    12     149 12.6   74     5   3
#4    18     313 11.5   62     5   4
#5    NA      NA 14.3   56     5   5
#6    28      NA 14.9   66     5   6
```

### 3. How many observations (term) in the date frame?
```
nrow(data)
#[1] 153
```

### 4. Print the last 10 terms of the frame date.
```
tail(data, 10)
#    Ozone Solar.R Wind Temp Month Day
#144    13     238 12.6   64     9  21
#145    23      14  9.2   71     9  22
#146    36     139 10.3   81     9  23
#147     7      49 10.3   69     9  24
#148    14      20 16.6   63     9  25
#149    30     193  6.9   70     9  26
#150    NA     145 13.2   77     9  27
#151    14     191 14.3   75     9  28
#152    18     131  8.0   76     9  29
#153    20     223 11.5   68     9  30
```

### 5. How many "NA" values in the "Ozone" column?
```
sum(is.na(data[, 1]))
#[1] 37
```

### 6. What is the mean of the Ozone column? Exclude "NA" value.
```
mean(data[,1], na.rm = TRUE)
#[1] 42.12931
```

### 7. Print the part of the data set (subset) with the value "Ozone"> 31 and "Temp"> 90. What is the mean value of "Solar.R" in this data set (subset)?
```
newdata <- subset(data, Ozone > 31 & Temp > 90)
mean(newdata[, 2])
#[1] 212.8
```

### 8. What is the mean value for "Temp" for June ("Month" is 6)?
```
mean(subset(data, Month == 6)[, 4])
#[1] 79.1
```

### 9. What is the maximum value of "Ozone" for May ("Month" is 5)?
```
max(subset(data, Month == 5)[, 1], na.rm = TRUE)
#[1] 115
```
