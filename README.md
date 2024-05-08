# Exercise 1
(((627+2)*3)-6)/3

# Exercise 2
a <- (627+2)
b <- a*3
c <- b-6
d <- c/3
rm(b)
d*3 == c
c+6 == b
b/3 == a

# Exercise 3
(((c(1,4,67,54,89)+2)*3)-6)/3

v1 <- c(1:5, b)
v1*1

v1 <- c(1:5, “b”)
v1*1

v1 <- c(1:5, T)
v1*1

# Exercise 4
a <- c(24,34,67)
b <- c(4,5,2)
c <- c(89,109,8)
d <- c(56,4,32)
e <- c(98,47,32)
 dat <- data.frame(a,b,c,d,e)
dat

sapply(dat, mean)

means <- numeric()
 for (col in colnames(dat)){
 means <- c(means, mean(dat[[col]]))
 }
means

# Exercise 5
group_n <- 1000
group <- c( rep("Group 1", group_n), rep("Group 2", group_n))
value <- c( rnorm(group_n, mean = 0), rnorm(group_n, mean = 4))
data <- data.frame(group,value)


ggplot(data, mapping = aes(x=value,y=value_2, color = group)) +
geom_point( position = "identity",alpha = .5) +
scale_fill_manual(values=c("#69b3a2","#404080"))+
theme_dark()+
facet_wrap(vars(group))

data$value_2 <- c( data[1:1000, "value"]*2 + rnorm(group_n, mean = 0) ,
data[1001:2000, "value"]*-.5 + rnorm(group_n, mean = 0) )

