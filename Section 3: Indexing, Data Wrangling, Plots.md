## Indexing
### Key Points
We can use logicals to index vectors.<br />
Using the function sum()on a logical vector returns the number of entries that are true.<br />
The logical operator “&” makes two logicals true only when they are both true.<br />
### Code
#defining murder rate as before<br />
murder_rate <- murders$total / murders$population * 100000<br />
#creating a logical vector that specifies if the murder rate in that state is less than or equal to 0.71<br />
index <- murder_rate <= 0.71<br />
#determining which states have murder rates less than or equal to 0.71<br />
murders$state[index]<br />
#calculating how many states have a murder rate less than or equal to 0.71<br />
sum(index)<br />

#creating the two logical vectors representing our conditions<br />
west <- murders$region == "West"<br />
safe <- murder_rate <= 1<br />
#defining an index and identifying states with both conditions true<br />
index <- safe & west<br />
murders$state[index]<br />

## Indexing Functions<br />
### Key Points<br />
The function **which()** gives us the entries of a logical vector that are true.<br />
The function **match()** looks for entries in a vector and returns the index needed to access them.<br />
We use the function **%in%** if we want to know whether or not each element of a first vector is in a second vector.<br />
### Code<br />
x <- c(FALSE, TRUE, FALSE, TRUE, TRUE, FALSE)<br />
which(x)    # returns indices that are TRUE<br />

#to determine the murder rate in Massachusetts we may do the following<br />
index <- which(murders$state == "Massachusetts")<br />
index<br />
murder_rate[index]<br />

#to obtain the indices and subsequent murder rates of New York, Florida, Texas, we do:<br />
index <- match(c("New York", "Florida", "Texas"), murders$state)<br />
index<br />
murders$state[index]<br />
murder_rate[index]<br />

x <- c("a", "b", "c", "d", "e")<br />
y <- c("a", "d", "f")<br />
y %in% x<br />

#to see if Boston, Dakota, and Washington are states<br />
c("Boston", "Dakota", "Washington") %in% murders$state<br />

## Basic Data Wrangling
### Key Points
To change a data table by adding a new column, or changing an existing one, we use the **mutate()** function.<br />
To filter the data by subsetting rows, we use the function **filter()**.<br />
To subset the data by selecting specific columns, we use the **select()** function.<br />
We can perform a series of operations by sending the results of one function to another function using the pipe operator, **%>%**.<br />
### Code
#installing and loading the dplyr package<br />
install.packages("dplyr")<br />
library(dplyr)<br />

#adding a column with mutate<br />
library(dslabs)<br />
data("murders")<br />
murders <- mutate(murders, rate = total / population * 100000)<br />

#subsetting with filter<br />
filter(murders, rate <= 0.71)<br />

#selecting columns with select<br />
new_table <- select(murders, state, region, rate)<br />

#using the pipe<br />
murders %>% select(state, region, rate) %>% filter(rate <= 0.71)<br />



