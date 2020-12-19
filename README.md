# Spark-foundation-TASK-
Data Analytics 
library("rpart")
library("dplyr")
library(rpart.plot)
indexes = sample(150)
#partion of data
iris_train = iris[indexes,]
iris_test = iris[indexes, ]
target = Species ~ Sepal.Length + Sepal.Width + Petal.Length + Petal.Width
##decision tree with rpart
tree = rpart(target, data = iris_train, method = "class")
rpart.plot(tree)
library(tidyverse)
library(caret)
library(rpart)
model <- rpart(Species ~., data = iris)
par(xpd = NA)
#predicition from model for particular class finding
newdata <- data.frame(Sepal.Length = 6.5, Sepal.Width = 3.0,Petal.Length = 5.2, Petal.Width = 2.0)
model %>% predict(newdata, "class")
