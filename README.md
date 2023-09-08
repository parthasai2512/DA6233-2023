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

