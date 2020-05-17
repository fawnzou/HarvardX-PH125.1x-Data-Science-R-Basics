## vectors
#We may create vectors of class numeric or character with the concatenate function<br />
codes <- c(380, 124, 818)<br />
country <- c("italy", "canada", "egypt")<br />

#We can also name the elements of a numeric vector<br />
#Note that the two lines of code below have the same result<br />
codes <- c(italy = 380, canada = 124, egypt = 818)<br />
codes <- c("italy" = 380, "canada" = 124, "egypt" = 818)<br />
<br />
#We can also name the elements of a numeric vector using the names() function<br />
codes <- c(380, 124, 818<br />
country <- c("italy","canada","egypt")<br />
names(codes) <- country<br />

#Using square brackets is useful for subsetting to access specific elements of a vector<br />
codes[2]<br />
codes[c(1,3)]<br />
codes[1:2]<br />

#If the entries of a vector are named, they may be accessed by referring to their name<br />
codes["canada"]<br />
codes[c("egypt","italy")]<br />

The function as.character() turns numbers into characters.<br />
The function as.numeric() turns characters into numbers.<br />
In R, missing data is assigned the value NA.<br />

## Sorting
### Key Points
The function sort() sorts a vector in increasing order.<br />
The function order() produces the indices needed to obtain the sorted vector, e.g. a result of  2 3 1 5 4 means the sorted vector will be produced by listing the 2nd, 3rd, 1st, 5th, and then 4th item of the original vector.<br />
The function rank() gives us the ranks of the items in the original vector.<br />
The function max() returns the largest value, while which.max() returns the index of the largest value. The functions min() and which.min() work similarly for minimum values.<br />
### Code<br />
library(dslabs)<br />
data(murders)<br />
sort(murders$total)<br />

x <- c(31, 4, 15, 92, 65)<br />
x<br />
sort(x)    #puts elements in order<br />

index <- order(x)    #returns index that will put x in order
x[index]    #rearranging by this index puts elements in order
order(x)

murders$state[1:10]<br />
murders$abb[1:10]<br />

index <- order(murders$total)<br />
murders$abb[index]    #order abbreviations by total murders<br />

max(murders$total)    #highest number of total murders<br />
i_max <- which.max(murders$total)    #index with highest number of murders<br />
murders$state[i_max]    #state name with highest number of total murders<br />

x <- c(31, 4, 15, 92, 65)
x
rank(x)    #returns ranks (smallest to largest)

