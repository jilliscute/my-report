# my-report
# regression's code
data<-read.csv(file.choose(),fileEncoding="big5")

plot(data$x5,data$y)

model=lm(data$y~data$x1+data$x2+data$x3+data$x4+data$x5,data=data,x=T)

anova(model)
summary(model)

out.forward<-regsubsets(data$y~data$x1+data$x2+data$x3+data$x4+data$x5,data=data,method="seqrep")
s.backward<-summary(out.backward)
s.s.backward<--round(cbind(s.backward$which,'rsq'==s.backward$rsq,'adjr2'=s.backward$adjr2,'rss'=s.backward$rss,'Cp'=s.backward$cp,'bic'=s.backward$bic),4)


install.packages("leaps")
library(leaps)
