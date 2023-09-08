# DA6233-2023
This is working after is reworking after a lot of times, consider as useful and original.

Today I have tested this and finally working(Commit,pull and push), good for next class.

class 1.
# getwd()- to get the working dir.
# ctrl+l- to clear.

# Quarto document(Document Format).


Yet another markup language(YAML)(Title, Author, format and editor)

mark down(the language of the web)

Heading Style:

H1 TO H6( #- H1 TO ######- H6)

print vs echo:

#Echo: is used to don't show the code - print only output.

# code chunk: its like adding new box to run the R code.

#Render the file: it is used to generate the HTML.

#Cntr+shift+enter- run the whole chunk.

# commenting:

Hash is used to comment- #.

1.is used to print the echo for print the code -#|
2.is used to print the eval not to instal the package again and again(avodi multiple installation) -#|

# calling library:

Load the library tidyverse by calling 'library()' function.
library(package name)


#Dataframe(table):

######mpg is a dataframe from ggplot2 package which we have installed from tidyverse.

# pandas(panel data analysis- use a API) in python is getting replaced with polar(dataframe).


head- top 6 rows
tail- last 6 rows
print- to print and use the dataframe.

dataframe- has vector(identical datatype and length of the rows for merging to table is required), it is usally of matrix form.- this condition is same for pandas and polar dataframe as well.

** how to impute the missing value replacing missing values in R is N/A(counted as data) and in python it is NULL.


# How to get pdf report from Rmarkdown using Knit:

1. install>> for latex package pdflatex>> install.packages('MiKTeX') before this install miktex software in the local systme and update the packages.
2. install >> rmarkdonw package>>install.packages('rmarkdown')
3.install>> tinyTex package tinytex::install_tinytex()
4. use rmarkdown and knit to generate pdf/word/html as required.

R - Algo 1- Assignment:


# (b)

#boxplot: MPG_Combo by Type 
boxplot(MPG_Combo ~ Type,data=cars, main="MPG_Combo by Type",xlab="Type",ylab = "MPG_Combo")
means <- tapply(cars$MPG_Combo, cars$Type, mean,na.rm=TRUE)
points(means, pch=22, col="blue")



shapiro.test(cars[cars$Type=="Sedan","MPG_Combo"])
shapiro.test(cars[cars$Type=="Sports","MPG_Combo"])
shapiro.test(cars[cars$Type=="SUV","MPG_Combo"])
shapiro.test(cars[cars$Type=="Truck","MPG_Combo"])
shapiro.test(cars[cars$Type=="Wagon","MPG_Combo"])

par(mfrow=c(1,1))
hist(cars[cars$Type=="Sedan","MPG_Combo"])
hist(cars[cars$Type=="Sports","MPG_Combo"])
hist(cars[cars$Type=="SUV","MPG_Combo"])
hist(cars[cars$Type=="Truck","MPG_Combo"])
hist(cars[cars$Type=="Wagon","MPG_Combo"])

summary(cars[cars$Type=="SUV","MPG_Combo"],na.rm=TRUE)
summary(cars[cars$Type=="Sports","MPG_Combo"],na.rm=TRUE)
summary(cars[cars$Type=="Sports","MPG_Combo"],na.rm=TRUE)
summary(cars[cars$Type=="Sports","MPG_Combo"],na.rm=TRUE)
summary(cars[cars$Type=="Sports","MPG_Combo"],na.rm=TRUE)




Algo Assignment -1:

# Student Name: Munivenkataparthasai Madallapalli
# Student Id: pua528
# HW1

# set your own path
setwd('D:\\UTSA\\Fall 2023\\Classes\\DA Algo 1\\Assignment') 

# set path is working
getwd()

#output:
#[1] "D:/UTSA/Fall 2023/Classes/DA Algo 1/Assignment"

######################################################
# Exercise 1
########################################################
# read dataset 

cars=read.csv("Cars.csv", header = TRUE) 

# (a)

# combined mpg varialbe 

MPG_Combo <- 0.6*cars$MPG_City+0.4*cars$MPG_Highway  

# data frame with MPG_Combo 

cars=data.frame(cars, MPG_Combo)  

#boxplot:

boxplot(cars$MPG_Combo,ylab="MPG_Combo")
points(mean(cars$MPG_Combo, na.rm=TRUE),col="blue",pch=22)


# (b)

#boxplot: MPG_Combo by Type 
boxplot(MPG_Combo ~ Type,data=cars, main="MPG_Combo by Type",xlab="Type",ylab = "MPG_Combo")
means <- tapply(cars$MPG_Combo, cars$Type, mean,na.rm=TRUE)
points(means, pch=22, col="blue")



#Algo 1 assignment fully done, refer below:
# Student Name: Munivenkataparthasai Madallapalli
# Student Id: pua528
# HW1

# set your own path
setwd('D:\\UTSA\\Fall 2023\\Classes\\DA Algo 1\\Assignment') 

# set path is working
getwd()

#output:
#[1] "D:/UTSA/Fall 2023/Classes/DA Algo 1/Assignment"

######################################################
# Exercise 1
########################################################
# read dataset 

cars=read.csv("Cars.csv", header = TRUE) 

# (a)

# combined mpg varialbe 

MPG_Combo <- 0.6*cars$MPG_City+0.4*cars$MPG_Highway  

# data frame with MPG_Combo 

cars=data.frame(cars, MPG_Combo)  

#boxplot:

boxplot(cars$MPG_Combo,ylab="MPG_Combo")
points(mean(cars$MPG_Combo, na.rm=TRUE),col="blue",pch=22)


# (b)

#boxplot: MPG_Combo by Type 
boxplot(MPG_Combo ~ Type,data=cars, main="MPG_Combo by Type",xlab="Type",ylab = "MPG_Combo")
means <- tapply(cars$MPG_Combo, cars$Type, mean,na.rm=TRUE)
points(means, pch=22, col="blue")

# (c) descriptive statistics for Horsepower for all vehicles
summary(cars$Horsepower,main="Horsepower",na.rm=TRUE)

#Visual Method:

#Histogram:
hist(cars$Horsepower,main="Horsepower",xlab="Horsepower")

#boxplot:
boxplot(cars$Horsepower,ylab="Horsepower")
points(mean(cars$Horsepower, na.rm=TRUE),col="blue",pch=22)

#qq plot:
qqnorm(cars$Horsepower); qqline(cars$Horsepower, col = 2)

#quantitative method:
#shapiro test:
shapiro.test(cars$Horsepower)


# (d)

#subset data for type

data_type<- subset(cars, Type %in% c("SUV", "Sports", "Truck"))


#Histogram:
hist(data_type$Horsepower,main="Horsepower By Type",xlab="Horsepower")
 
#boxplot: Horsepower by Type 
boxplot(Horsepower~ Type,data=data_type, main="Horsepower by Type",xlab="Type",ylab = "Horsepower")
means <- tapply(data_type$Horsepower, data_type$Type, mean,na.rm=TRUE)
points(means, pch=22, col="blue")


 
#qq plot:
qqnorm(data_type$Horsepower); qqline(data_type$Horsepower, col = 2)
 
#quantitative method:
# Shapiro-Wilk test for Sports:
shapiro.test(data_type$Horsepower[data_type$Type == "Sports"])

# Shapiro-Wilk test for SUV
shapiro.test(data_type$Horsepower[data_type$Type == "SUV"])

# Shapiro-Wilk test for Truck
shapiro.test(data_type$Horsepower[data_type$Type=="Truck"])
 
#2.(C)
#subsetting the data for cars(SUV & Truck)
data_type_test<- subset(cars, Type %in% c("SUV","Truck"))

# Performing wilcox Test
wilcox.test(Horsepower ~ Type, data=data_type_test, exact=FALSE)

#3.(a)

#installing required packages for filtering:
install.packages("dplyr")
library(dplyr)
#filtering the data for airquality:
airquality_filter.july=airquality %>% filter(airquality$Month==7)
airquality_filter.august=airquality %>% filter(airquality$Month==8)

#pan divisiion for qq-plot:

par(mfrow=c(1,2))

# QQ Plot for wind-July
qqnorm(airquality_filter.july$Wind,main = "QQ Plot for airquality_filter.july",ylab="Wind speed in MPH")
qqline(airquality_filter.july$Wind,col="red")


# QQ Plot for wind-August
qqnorm(airquality_filter.august$Wind,main = "QQ Plot for airquality_filter.august",ylab = "Wind speed in MPH")
qqline(airquality_filter.august$Wind,col="red")

#quantitative method:
# Shapiro-Wilk test:

shapiro.test(airquality_filter.july$Wind)
shapiro.test(airquality_filter.august$Wind)

# combining july and august data to perform variance:
Combined_july_august=union(airquality_filter.july,airquality_filter.august)

#equal variance test: 
var.test(Combined_july_august$Wind ~ Combined_july_august$Month, alternative="two.sided")

#run pooled t-test
t.test(Combined_july_august$Wind ~ Combined_july_august$Month,alternative="two.sided",var.equal=TRUE)

