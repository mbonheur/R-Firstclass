---
title: "1st Class"
output: html_document
date: "2025-10-15"
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```

```{r}
#numeric
x<-c(0.5,0.6)
age<-c(20,35,32,29)
summary(age)
```
```{r}
age<-c(35,24,18,24)
mean(age)
```
```{r}
#logical 
x<-c(TRUE,FALSE)
X<-c(T,F)
X
```
```{r}
#Character
X<-c("a","b","c")
class<-c("M","F","F","M")
class

```
```{r}
#integer
x<-9:29
x
```
```{r}
#Complex
x<-c(1+0i,2+4i)
x
```
```{r}
#Matrix and operation within matrices
x<-matrix(1:6,nrow =2,ncol = 3 )
x
```
```{r}
(y<-matrix(1:6,nrow = 3,ncol = 2))
```
```{r}
x%*%y
```
```{r}
#List 
x<-list(1,"a",TRUE,1+4i)
x
```
```{r}
#factor
x<-factor(c("yes","yes","no","yes","no"))
x
```
```{r}
#Create a vector with NAsin it
x<-c(1,2,NA,10,3)
is.na(x)
```
```{r}
x<-c(1,2,4,"NA",5)
bad<-is.na(x)
print(bad)
x[!bad]
```
```{r}
x<-c(1,2,NA,4,NA,5)
y<-c("a","b",NA,"d",NA,"f")
good<-complete.cases(x,y)
good
```
```{r}
#Coercion
sum(c(TRUE,TRUE,FALSE,FALSE,FALSE))
```
```{r}
#Create data
StudentID<-c(1,2,3,4,5)
math_score<-c(12,17,10,9,NA)
gender<-c("M","F","M","M","F")
it_score<-c(13,18,11,10,19)
scoredata<-data.frame(StudentID,gender,math_score,it_score)
scoredata
```
