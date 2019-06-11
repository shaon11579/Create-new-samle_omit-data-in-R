# Create-new-samle_omit-data-in-R

setwd("C:/Users/30778022/Desktop")
#
mydata2 <- read.csv("Inventory.900.CSV", TRUE, ",")
mydata <- read.csv("LGv1.CSV", TRUE, ",")
mydata3 <- read.csv("Inventory900.CSV", TRUE, ",")
mydata3.new <- mydata3[1:6]
#
summary(mydata3.new)
any(is.na(mydata3.new))
str(mydata3.new)
head(mydata3.new)
tail(mydata3.new)
sum(is.na(mydata3.new))
nrow(mydata3.new)
sum(is.na(mydata3.new$Forecasting.Bias))
colSums(is.na(mydata3.new))

#
mydata3.clean <- na.omit(mydata3.new)
nrow(mydata3.clean)
mydata3.clean2 <- mydata3.new [complete.cases(mydata3.new),]
