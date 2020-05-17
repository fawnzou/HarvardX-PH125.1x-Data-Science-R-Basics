## vectors
#We may create vectors of class numeric or character with the concatenate function
codes <- c(380, 124, 818)
country <- c("italy", "canada", "egypt")

#We can also name the elements of a numeric vector
#Note that the two lines of code below have the same result
codes <- c(italy = 380, canada = 124, egypt = 818)
codes <- c("italy" = 380, "canada" = 124, "egypt" = 818)

#We can also name the elements of a numeric vector using the names() function
codes <- c(380, 124, 818)
country <- c("italy","canada","egypt")
names(codes) <- country

#Using square brackets is useful for subsetting to access specific elements of a vector
codes[2]
codes[c(1,3)]
codes[1:2]

#If the entries of a vector are named, they may be accessed by referring to their name
codes["canada"]
codes[c("egypt","italy")]

The function as.character() turns numbers into characters.
The function as.numeric() turns characters into numbers.
In R, missing data is assigned the value NA.

## Sorting
### Key Points
The function sort() sorts a vector in increasing order.
The function order() produces the indices needed to obtain the sorted vector, e.g. a result of  2 3 1 5 4 means the sorted vector will be produced by listing the 2nd, 3rd, 1st, 5th, and then 4th item of the original vector.
The function rank() gives us the ranks of the items in the original vector.
The function max() returns the largest value, while which.max() returns the index of the largest value. The functions min() and which.min() work similarly for minimum values.
### Code
library(dslabs)
data(murders)
sort(murders$total)

x <- c(31, 4, 15, 92, 65)
x
sort(x)    #puts elements in order

index <- order(x)    #returns index that will put x in order
x[index]    #rearranging by this index puts elements in order
order(x)

murders$state[1:10]
murders$abb[1:10]

index <- order(murders$total)
murders$abb[index]    #order abbreviations by total murders

max(murders$total)    #highest number of total murders
i_max <- which.max(murders$total)    #index with highest number of murders
murders$state[i_max]    #state name with highest number of total murders

x <- c(31, 4, 15, 92, 65)
x
rank(x)    #returns ranks (smallest to largest)

