path <- function (directory, id) {
  fileName <- id
  if (id < 10) {
    fileName <- paste("00", id, sep="")
  }
  else if (id < 100) {
    fileName <- paste("0", id, sep="")
  }
  filePath <- paste(fileName, ".csv", sep="")
  resultPath <- paste(directory, filePath, sep="/")
  resultPath
}

# 1 Write a pmean function that calculates the mean value of sulfate or nitrate contamination among a given list of monitors. This function takes three arguments: "directory", "pollutant", "id". Directory - the folder where the data is located, pollutant - type of pollution, id - list of monitors. The id argument has a default value of 1: 332. The function must ignore the NA value.
pmean <- function(directory, pollutant, id = 1:332) {
  data
  for (i in id) {
    newData <- read.csv(file=path(directory, i))
    if (typeof(data) == "list") {
      data <- rbind(data, newData)
    }
    else {
      data <- newData
    }
  }
  mean(data[, paste(pollutant)], na.rm = TRUE)
}

c <- pmean("specdata", "sulfate", 1:10)
# [1] 4.064128
d <- pmean("specdata", "nitrate")
d
# [1] 1.702932

# 2 Write a complete function that displays the number of completely observed cases for each file. The function takes two arguments: "Directory" and "id" and returns a data frame in which the first column is the file name and the second is the number of full observations.
complete <- function (directory, id) {
  data
  for (i in id) {
    newData <- read.csv(file=path(directory, i))
    nobs <- nrow(na.omit(newData))
    if (typeof(data) == "list"){
      data <- rbind(data, data.frame(id = i, nobs))
    }
    else {
      data <- data.frame(id = i, nobs)
    }
  }
  data
}
complete("specdata", 1)
complete("specdata", c(2, 4, 8, 10, 12))
complete("specdata", 50:60)

# 3 Write a corr function that takes two arguments: directory (the folder where the observation files are located) and threshold (the threshold value is 0 by default) and calculates the correlation between sulfates and nitrates for monitors for which the number of complete observations is greater than the threshold value. The function must return a vector of correlation values. If no monitor exceeds the threshold, the function should return a numeric vector of length 0. Use the built-in function to calculate the correlation between sulfates and nitrates. "Cor" with default settings.

corr <- function (directory, threshold = 0) {
  result <- c()
  for (i in 1:332) {
    data <- read.csv(file = path(directory, i))
    cleanData <- na.omit(data)
    if (nrow(cleanData) > threshold) {
      result <- c(result, cor(cleanData[, 2], cleanData[, 3]))
    }
  }
  result
}

cr <- corr("specdata", 150)
head(cr)
summary(cr)

cr <- corr("specdata", 400)
head(cr)
summary(cr)

cr <- corr("specdata", 5000)
head(cr)
summary(cr)
length(cr)


