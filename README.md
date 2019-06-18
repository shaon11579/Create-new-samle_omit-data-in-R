# Create-new-sample_omit-data-in-R
# Set working di
setwd("C:/Users/30778022/Desktop")
# Read data from CSV file 
mydata2 <- read.csv("Inventory.900.CSV", TRUE, ",")
mydata <- read.csv("LGv1.CSV", TRUE, ",")
mydata3 <- read.csv("Inventory900.CSV", TRUE, ",")
# Create a new smaple data set from existing data st, in this case first three twas 
mydata3.new <- mydata3[1:6]
#
summary(mydata3.new)
any(is.na(mydata3.new))
str(mydata3.new)
# check head and tail of the new data set 
head(mydata3.new)
tail(mydata3.new)
# check summary and number of raws in the new data set 
sum(is.na(mydata3.new))
nrow(mydata3.new)

# check number of missing values in certail raws, in this case it is forcasting bias 
sum(is.na(mydata3.new$Forecasting.Bias))
# find missing values in all raws 
colSums(is.na(mydata3.new))

# clean missing values from the data 
mydata3.clean <- na.omit(mydata3.new)

# Nrow of the clean data 
nrow(mydata3.clean)
# updated clean data 
mydata3.clean2 <- mydata3.new [complete.cases(mydata3.new),]
