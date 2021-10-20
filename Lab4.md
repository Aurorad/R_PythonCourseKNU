data <- read.csv(file = "hw1_data.csv",  stringsAsFactors=FALSE)
data

## 1.What are the column names of the data file?
names(data)

## 2. Print the first 6 lines of the data frame.
data[1:6,]

## 3. How many observations (term) in the date frame?
nrow(data)

## 4. Print the last 10 terms of the frame date.
tail(data, 10)

## 5. How many "NA" values in the "Ozone" column?
sum(is.na(data[, 1]))

## 6. What is the mean of the Ozone column? Exclude "NA" value.
mean(data[,1], na.rm = TRUE)

## 7. Print the part of the data set (subset) with the value "Ozone"> 31 and "Temp"> 90. What is the mean value of "Solar.R" in this data set (subset)?
newdata <- subset(data, Ozone > 31 & Temp > 90)
newdata
mean(newdata[, 2])

## 8. What is the mean value for "Temp" for June ("Month" is 6)?
mean(subset(data, Month == 6)[, 4])

## 9. What is the maximum value of "Ozone" for May ("Month" is 5)?
max(subset(data, Month == 5)[, 1], na.rm = TRUE)
