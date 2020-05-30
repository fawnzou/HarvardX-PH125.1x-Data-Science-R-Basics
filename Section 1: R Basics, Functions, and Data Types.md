
## Code: using install.packages and library()<br />

#installing the dslabs package<br />
install.packages("dslabs")<br />
#loading the dslabs package into the R session<br />
library(dslabs)<br />

### You can add the option dependencies = TRUE, which tells R to install the other things that are necessary for the package or packages to run smoothly. Otherwise, you may need to install additional packages to unlock the full functionality of a package.<br />
### Keyboard shortcuts:<br />
Save a script: Ctrl+S on Windows and Command+S on Mac<br />
Run an entire script:  Ctrl+Shift+Enter on Windows Command+Shift+Return on Mac, or click "Source" on the editor pane<br />
Run a single line of script: Ctrl+Enter on Windows and Command+Return on Mac while the cursor is pointing to that line, or select the chunk and click "run"<br />
Open a new script: Ctrl+Shift+N on Windows and Command+Shift+N on Mac<br />

### Key Points<br />
To define a variable, we may use the assignment symbol, <-.<br />
There are two ways to see the value stored in a variable:<br />
(1) type the variable name into the console and hit Return, <br />
(2) use the print() function by typing print(variable_name) and hitting Return.<br />
Objects are things that are stored in named containers in R.  They can be variables, functions, etc.<br />
The ls() function shows the names of the objects saved in your workspace.<br />

## Data type <br />

#loading the dslabs package and the murders dataset<br />
library(dslabs)<br />
data(murders)<br />

#determining that the murders dataset is of the "data frame" class<br />
class(murders)<br />
#finding out more about the structure of the object<br />
str(murders)<br />
#showing the first 6 lines of the dataset<br />
head(murders)<br />

#using the accessor operator to obtain the population column<br />
murders$population<br />
# displaying the variable names in the murders dataset<br />
names(murders)<br />
#determining how many entries are in a vector<br />
pop <- murders$population<br />
length(pop)<br />
#vectors can be of class numeric and character<br />
class(pop)<br />
class(murders$state)<br />

#logical vectors are either TRUE or FALSE<br />
z <- 3 == 2<br />
z<br />
class(z)<br />

#factors are another type of class<br />
class(murders$region)<br />
# obtaining the levels of a factor<br />
levels(murders$region)<br />


