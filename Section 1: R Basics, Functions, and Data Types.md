
## Code: using install.packages and library()

#installing the dslabs package
install.packages("dslabs")
#loading the dslabs package into the R session
library(dslabs)

### You can add the option dependencies = TRUE, which tells R to install the other things that are necessary for the package or packages to run smoothly. Otherwise, you may need to install additional packages to unlock the full functionality of a package.
### Keyboard shortcuts:
Save a script: Ctrl+S on Windows and Command+S on Mac
Run an entire script:  Ctrl+Shift+Enter on Windows Command+Shift+Return on Mac, or click "Source" on the editor pane
Run a single line of script: Ctrl+Enter on Windows and Command+Return on Mac while the cursor is pointing to that line, or select the chunk and click "run"
Open a new script: Ctrl+Shift+N on Windows and Command+Shift+N on Mac

### Key Points
To define a variable, we may use the assignment symbol, <-.
There are two ways to see the value stored in a variable: (1) type the variable name into the console and hit Return, or (2) use the print() function by typing print(variable_name) and hitting Return.
Objects are things that are stored in named containers in R.  They can be variables, functions, etc.
The ls() function shows the names of the objects saved in your workspace.

## Data type

#loading the dslabs package and the murders dataset
library(dslabs)
data(murders)

#determining that the murders dataset is of the "data frame" class
class(murders)
#finding out more about the structure of the object
str(murders)
#showing the first 6 lines of the dataset
head(murders)

#using the accessor operator to obtain the population column
murders$population
# displaying the variable names in the murders dataset
names(murders)
#determining how many entries are in a vector
pop <- murders$population
length(pop)
#vectors can be of class numeric and character
class(pop)
class(murders$state)

#logical vectors are either TRUE or FALSE
z <- 3 == 2
z
class(z)

#factors are another type of class
class(murders$region)
# obtaining the levels of a factor
levels(murders$region)


