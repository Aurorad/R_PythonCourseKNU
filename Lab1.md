## 1. �������� ���� ������� (atomic) ����. ����� ����: character, numeric, integer, complex, logical.
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

## 2. �������� �������, ��: ������ ����������� � 5 �� 75; ������ ����� 3.14, 2.71, 0, 13; 100 ������� TRUE.
b0 <- 5:75
b0
b1 <- c(3.14, 2.71, 0.13)
b1
b2 <- as.logical(1:101)
b2

## 3. �������� �������� ������� �� ��������� matrix, �� �� ��������� cbind ��� rbind
col0 <- c(0.5, 3.9, 0, 2)
col1 <- c(1.3, 131, 2.2, 7)
col2 <- c(3.5, 2.8, 4.6, 5.1)
c <- cbind(col0, col1, col2)
c

## 4. �������� �������� ������ (list), � ���� �������� �� ����� ����.
d <- list(a0, a1, a2, a3, a4)
d

## 5. �������� ������ � ������ ������ �baby�, �child�, �adult�.
e <- factor(c("baby", "child", "adult", "child", "adult"),
  levels = c("baby", "child", "adult"))
e
table(e)

## 6. ������ ������ ������� �������� NA � ������ 1, 2, 3, 4, NA, 6, 7, NA, 9, NA, 11. ������ ������� ������� NA.
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

## 7. �������� �������� data frame �� ������� � �������.
g <- data.frame(id = 1:3, name = c("Kate", "Tom", "John"), age = c(15, 17, 12))
g

## 8. ������ ����� �������� ����� data frame.
names(g)[1] <- "ID"
names(g)[2] <- "NAME"
names(g)[3] <- "AGE"
g

