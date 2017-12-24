# my-report:regression

######The file have x1~x5 and  y
######We want to discuss whether they have relationship or not
---------------
* read files
>data<-read.csv(file.choose(),fileEncoding="big5")

* draw scatter plot
>plot(data$x1,data$y)
>plot(data$x2,data$y)
>plot(data$x3,data$y)
>plot(data$x4,data$y)
>plot(data$x5,data$y)

* build a model
>model=lm(data$y~data$x1+data$x2+data$x3+data$x4+data$x5,data=data,x=T)
>anova(model)
>summary(model)


out.forward<-regsubsets(data$y~data$x1+data$x2+data$x3+data$x4+data$x5,data=data,method="seqrep")
s.backward<-summary(out.backward)
s.s.backward<--round(cbind(s.backward$which,'rsq'==s.backward$rsq,'adjr2'=s.backward$adjr2,'rss'=s.backward$rss,'Cp'=s.backward$cp,'bic'=s.backward$bic),4)


install.packages("leaps")
library(leaps)
