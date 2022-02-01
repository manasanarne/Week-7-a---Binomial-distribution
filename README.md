# Week-7-a---Binomial-distribution
x<-c(0,1,2,3,4,5,6)
f<-c(7,64,140,210,132,75,12)
fx<-f*x
sumfx<-sum(f*x)
print(sumfx)
sumf<-sum(f)
print(sumf)
s<-length(x)-1
p=sumfx/sumf/s
print(p)
pr<-dbinom(0:6,size=s,prob=p)
pr<-round(pr,digits=5)
fee<-(pr*sumf)
fe<-round(fee,digits=0)
mydata<- data.frame(x,f,fx,pr,fee,fe)
print(mydata)
sums<-list(NA,sum(f),sum(f*x),NA,NA,sum(fe))
mydata<-rbind(mydata,sums)
print(mydata,row.names=FALSE)
result<-chisq.test(f,p=pr,rescale.p=TRUE)
print(result)
tablevalue<-qchisq(.95, df=s)
print(tablevalue)

OUTPUT:-
Table value is  12.59159

