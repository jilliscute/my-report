# my-report:regression
--------------
###### The file have x1~x5 and  y
###### We want to discuss whether they have relationship or not
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
```model=lm(data$y~data$x1+data$x2+data$x3+data$x4+data$x5,data=data,x=T)
anova(model)
summary(model)```

