## Basic Conditionals
### Key Point
The most common conditional expression in programming is an if-else statement, which has the form "if [condition], perform [expression], else perform [alternative expression]". <br />
The ifelse() function works similarly to an if-else statement, but it is particularly useful since it works on vectors by examining each element of the vector and returning a corresponding answer accordingly. <br />
The any() function takes a vector of logicals and returns true if any of the entries are true. <br />
The all() function takes a vector of logicals and returns true if all of the entries are true. <br />
### Code
#an example showing the general structure of an if-else statement <br />
a <- 0 <br />
if(a!=0){ <br />
  print(1/a) <br />
} else{ <br />
  print("No reciprocal for 0.") <br />
} <br />

#an example that tells us which states, if any, have a murder rate less than 0.5 <br />
library(dslabs) <br />
data(murders) <br />
murder_rate <- murders$total / murders$population*100000 <br />
ind <- which.min(murder_rate) <br />
if(murder_rate[ind] < 0.5){ <br />
  print(murders$state[ind])  <br />
} else{ <br />
  print("No state has murder rate that low") <br />
} <br />

#changing the condition to < 0.25 changes the result <br />
if(murder_rate[ind] < 0.25){ <br />
  print(murders$state[ind])  <br />
} else{ <br />
  print("No state has a murder rate that low.") <br />
} <br />

#the ifelse() function works similarly to an if-else conditional <br />
a <- 0 <br />
ifelse(a > 0, 1/a, NA) <br />

#the ifelse() function is particularly useful on vectors <br />
a <- c(0,1,2,-4,5) <br />
result <- ifelse(a > 0, 1/a, NA) <br />

#the ifelse() function is also helpful for replacing missing values <br />
data(na_example) <br />
no_nas <- ifelse(is.na(na_example), 0, na_example)  <br />
sum(is.na(no_nas)) <br />

#the any() and all() functions evaluate logical vectors <br />
z <- c(TRUE, TRUE, FALSE) <br />
any(z) <br />
all(z) <br />
