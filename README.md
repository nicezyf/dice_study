# dice_study
#Simulated craps
roll <- function(x=1:6){  m <- sample(x = x,size = 3,replace = TRUE)  
sum(m)}#重复投掷骰子
rolls <- replicate(n = 10000,expr = roll())
qplot(rolls,binwidth=1)
rolls <- as.data.table(rolls)
a <- rolls[rolls<=6,]#添加权重
roll <- function(x=1:6){  m <- sample(x = x,size = 2,replace = TRUE,prob = c(1/8,1/8,1/8,1/8,1/8,3/8))  
sum(m)}rolls <- replicate(n = 10000,expr = roll())
qplot(rolls,binwidth=1)rolls <- as.data.table(rolls)
a <- rolls[rolls<=6,]
