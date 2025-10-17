---
title: "1st Class"
output: html_document
date: "2025-10-15"
---
Data structure (Vectors, Factors, Lists, Data frame, matrix and arrays)
Vector: The foundational R data structure
```{r}
##Numeric
x <- c(0.5, 0.6)
age<-c(20,35,32,29)
summary(age)
```
```{r}
age<-c(35,24,18,24)
mean(age)
```
```{r}
## Logical
x <- c(TRUE, FALSE)
x <- c(T, F)
## Character
x<-c("a","b","c")
class<-c("M","F","F","M")
##Integer
x<-9:29
##Complex
x<-c(1+0i,2+4i)
```
```{r}
## Matrix and operation within matrices
x<-matrix(1:6,nrow=2,ncol=3)
x
```
```{r}
(y<-matrix(1:6,nrow=3,ncol=2))
```
```{r}
 x%*%y
```
```{r}
## List
x<-list(1,"a",TRUE,1+4i)
x
```
```{r}
## Factor
x<-factor(c("yes","yes","no","yes","no"))
## Create a vector with NAs init
x<-c(1,2,NA,10,3)

```
```{r}
## Return a logical vector indicating which elements are NA
is.na(x)
x<-c(1,2,4,"NA",5)
bad<-is.na(x)
print(bad)
```
What if there are multiple R objects and you want to take the subset with no missing values in any of those objects?
```{r}
 x<-c(1,2,NA,4,NA,5)
 y<-c("a","b",NA,"d",NA,"f")
 good<-complete.cases(x,y)
 good
```
Coercion

If character is present,in a vector,R convert everything in the vector to character strings.
If a vector only contains logical and numbers,R will convert the logical to numbers,
Every true becomes a1,and every FALSE becomes 0

```{r}
sum(c(TRUE,TRUE,FALSE,FALSE,FALSE))
```
Create data
Create data Using dataframe Dataframe is more general than matrix How???
Because dataframe can contain different modes of data (Numeric,character and so on)Similar  to what you can see in SPSS,SAS,…
 
```{r}
### Let’s create a dataframe
studentID<-c(1,2,3,4,5)
math_score<-c(12,17,10,9,NA)
gender<-c("M","F","M","M","F")
it_score<-c(13,18,11,10,19)
scoredata<-data.frame(studentID,gender,math_score,it_score)
scoredata
#View(scoredata)
```
Create data from keyboard
Steps1. Create dataframe(or matrix) with variable names2.Invoke the text editor
in the data objected created at first step
```{r}
data_class2<-data.frame(height=numeric(0),weight=numeric(0),bmi=numeric
 (0))
 data_class2<-edit(data_class2)
```
DataImportation
Rhassomefeaturesthatcanallowtoimportdatafromdifferentsources(Itcanbe
textfile,spreadsheet,ordatabase)
 1. Datafromexcel
 2. Datastatisticalpackages(SAS,SPSS,Stata)
 3. DatafromTextfiles(ASCII,XML,Webscraping)
 4. Datafromdatabasemanagementsystems(SQL,MySQL,Oracle,Access)
```{r}
variable.names(women)
head(women)
tail(women)
women[10:20,]
summary(women$WEIGHT)
length(women$WEIGHT)
women[,-1]
```
In case you want to use dataset built in R
```{r}
 data()#listofdatasetscurrentlyavailable
 data("airquality")
 variable.names(airquality)
 str(airquality)
 summary(airquality)
 
```
Summary Statistics
```{r}
summary(women)
apply(women,2,mean)
apply(women,2,sd)
c(mean(women$HEIGHT),sd(women$HEIGHT))
c(mean(women$WEIGHT),sd(women$WEIGHT))
c(Mean=mean(women$HEIGHT),SD=sd(women$HEIGHT))
c(Mean=mean(women$WEIGHT),SD=sd(women$WEIGHT))
```
Variation and covariation using both numerical and graphs
Relationship between a categorical and a continuous variable
```{r}
data("iris")
head(iris)
mean(iris$Petal.Length)
mean(iris$Petal.Length[iris$Species=="setosa"])
mean(iris$Petal.Length[iris$Species=="versicolor"])
mean(iris$Petal.Length[iris$Species=="virginica"])

#Shortcut
by(iris$Petal.Length,iris$Species,mean)
by(iris$Petal.Length,iris$Species,sd)
by(iris$Petal.Length,iris$Species,summary)

#Visualize the differences in continuous variables between categories using Box-and whisker plot
boxplot(iris$Sepal.Length~iris$Species,data=iris, main="Comparison")

```
Relationship between two categorical variables
```{r}
ucba<-data.frame(UCBAdmissions)
head(ucba)
```
```{r}
cross<-xtabs(Freq~Gender+Admit,data=ucba)
(cross<-xtabs(Freq~Gender+Admit,data=ucba))
```
```{r}
##IstheregenderbiasinUCBgraduateadmissionprocess?
 prop.table(cross,2)
```
Simpson’sparadox
Phenomenon,whereatrendthatappearsincombinedgroupsofdatadisappearsor reverseswhenbrokendownintogroups.
```{r}
cross2<-xtabs(Freq~Gender+Admit,data=ucba[ucba$Dept=="A",])
 prop.table(cross2,1)
```
BarChart
```{r}
dat<-read.table(text="ProdAProdBProdCProdD
 1110506070
 2120508065",header=TRUE)
 barplot(as.matrix(dat),beside=FALSE,col=c("Red","green"))
```
```{r}
#barplot(as.matrix(dat),beside=TRUE,col=c("gold3","red"))
 dat <- read.table(text = "A B C D E F G
 1 10 80 30 90 70 60 90
 2 20 50 70 50 40 10 40
 3 60 80 80 60 60 30 160
 4 20 40 70 80 20 10 70", header = TRUE)
 barplot(as.matrix(dat))

```
Scatter Plot
```{r}
plot(women[,1],women[,2])
```
