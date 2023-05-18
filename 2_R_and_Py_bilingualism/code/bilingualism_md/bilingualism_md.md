# R and Python bilingualism

Welcome to the R and Python bilingualism reference guide! If you’re
fluent in one of these languages but hesitant to learn the other, you’re
in the right place. The good news is that there are many similarities
between R and Python that make it easy to switch between the two.

Both R and Python are widely used in data science and are open-source,
meaning that they are free to use and constantly being improved by the
community. They both have extensive libraries for data analysis,
visualization, and machine learning. In fact, many of the libraries in
both languages have similar names and functions, such as Pandas in
Python and data.table in R.

While there are differences between the two languages, they can
complement each other well. Python is versatile and scalable, making it
ideal for large and complex projects such as web development and
artificial intelligence. R, on the other hand, is known for its
exceptional statistical capabilities and is often used in data analysis
and modeling. Visualization is also easier in R, making it a popular
choice for creating graphs and charts.

By learning both R and Python, you’ll be able to take advantage of the
strengths of each language and create more efficient and robust data
analysis workflows. Don’t let the differences between the two languages
intimidate you - once you become familiar with one, learning the other
will be much easier.

So, whether you’re a Python enthusiast looking to expand your
statistical analysis capabilities, or an R user interested in exploring
the world of web development and artificial intelligence, this guide
will help you become bilingual in R and Python.

## Install packages

In R, packages can be installed from CRAN repository by using the
install.packages() function:

R code:

``` r
# Install the dplyr package from CRAN
install.packages("dplyr")
```

In Python, packages can be installed from the Anaconda repository by
using the conda install command:

Python code:

``` python
# Install the pandas package from Anaconda
!conda install pandas
```

Loading libraries in R and Python

In R, libraries can be loaded in the same way as before, using the
library() function:

R code:

``` r
# Load the dplyr library
library(dplyr)
```

In Python, libraries can be loaded in the same way as before, using the
import statement. Here’s an example:

Python code:

``` python
# Load the pandas library
import pandas as pd
```

Note that the package or library must be installed from the respective
repository before it can be loaded. Also, make sure you have the correct
repository specified in your system before installing packages. By
default, R uses CRAN as its primary repository, whereas Anaconda uses
its own repository by default.

## reticulate

The reticulate package lets you run both R and Python together in the R
environment.

R libraries are stored and managed in a repository called CRAN. You can
download R packages with the install.packages() function

``` r
install.packages("reticulate")
```

You only need to install packages once, but you need to mount those
packages with the library() function each time you open R.

``` r
library(reticulate)
```

Python libraries are stored and managed in a few different libraries and
their dependencies are not regulated as strictly as R libraries are in
CRAN. It’s easier to publish a python package but it can also be more
cumbersome for users because you need to manage dependencies yourself.
You can download python packages using both R and Python code

``` r
py_install("laspy")
```

    ## + '/Users/ty/opt/miniconda3/bin/conda' 'install' '--yes' '--prefix' '/Users/ty/opt/miniconda3/envs/earth-analytics-python' '-c' 'conda-forge' 'laspy'

Now, let’s create a Python list and assign it to a variable py_list:

R code:

``` r
py_list <- r_to_py(list(1, 2, 3))
```

We can now print out the py_list variable in Python using the
py_run_string() function:

R code:

``` r
py_run_string("print(r.py_list)")
```

This will output \[1, 2, 3\] in the Python console.

Now, let’s create an R vector and assign it to a variable r_vec:

R code:

``` r
r_vec <- c(4, 5, 6)
```

We can now print out the r_vec variable in R using the py$ syntax to
access Python variables:

R code:

``` r
print(py$py_list)
```

This will output \[1, 2, 3\] in the R console.

We can also call Python functions from R using the py_call() function.
For example, let’s call the Python sum() function on the py_list
variable and assign the result to an R variable r_sum:

R code:

``` r
r_sum <- py_call("sum", args = list(py_list))
```

We can now print out the r_sum variable in R:

R code:

``` r
print(r_sum)
```

This will output 6 in the R console.

## Load packages and change settings

``` r
options(java.parameters = "-Xmx5G")

library(r5r)
library(sf)
library(data.table)
library(ggplot2)
library(interp)
library(dplyr)
library(osmdata)
library(ggthemes)
library(sf)
library(data.table)
library(ggplot2)
library(akima)
library(dplyr)
library(raster)
library(osmdata)
library(mapview)
library(cowplot)
library(here)
library(testthat)
```

``` python
import sys
sys.argv.append(["--max-memory", "5G"])

import pandas as pd
import geopandas
import matplotlib.pyplot as plt
import numpy as np
import plotnine
import contextily as cx
import r5py
import seaborn as sns
```

R and Python are two popular programming languages used for data
analysis, statistics, and machine learning. Although they share some
similarities, there are some fundamental differences between them.
Here’s an example code snippet in R and Python to illustrate some of the
differences:

R Code:

``` r
# Create a vector of numbers from 1 to 10
x <- 1:10

# Compute the mean of the vector
mean_x <- mean(x)

# Print the result
print(mean_x)
```

    ## [1] 5.5

Python Code:

``` python
# Import the numpy library for numerical operations
import numpy as np

# Create a numpy array of numbers from 1 to 10
x = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9, 10])

# Compute the mean of the array
mean_x = np.mean(x)

# Print the result
print(mean_x)
```

    ## 5.5

In this example, we can see that there are several differences between R
and Python:

Syntax: R uses the assignment operator \<- while Python uses the equals
sign = for variable assignment.

Libraries: Python relies heavily on external libraries such as numpy,
pandas, and matplotlib for data analysis, while R has built-in functions
for many data analysis tasks.

Data types: R is designed to work with vectors and matrices, while
Python uses lists and arrays. In the example above, we used the numpy
library to create a numerical array in Python.

Function names: Function names in R and Python can differ significantly.
In the example above, we used the mean() function in R and the np.mean()
function in Python to calculate the mean of the vector/array.

These are just a few of the many differences between R and Python.
Ultimately, the choice between the two languages will depend on your
specific needs and preferences.

## Load saved data

R Code:

``` r
data("iris")
here()
load(file=here("2_R_and_Py_bilingualism", "data", "iris_example_data.rdata"))
objects()
```

Python code:

## Save data

R Code:

``` r
save(iris, file=here("2_R_and_Py_bilingualism", "data", "iris_example_data.rdata"))

write.csv(iris, file=here("2_R_and_Py_bilingualism", "data", "iris_example_data.csv"))
```

Python code:

## functions

Both R and Python are powerful languages for writing functions that can
take input, perform a specific task, and return output. R Code:

``` r
# Define a function that takes two arguments and returns their sum
sum_r <- function(a, b) {
  return(a + b)
}

# Call the function with two arguments and print the result
result_r <- sum_r(3, 5)
print(result_r)
```

    ## [1] 8

Python code:

``` python
# Define a function that takes two arguments and returns their sum
def sum_py(a, b):
    return a + b

# Call the function with two arguments and print the result
result_py = sum_py(3, 5)
print(result_py)
```

    ## 8

In both cases, we define a function that takes two arguments and returns
their sum. In R, we use the function keyword to define a function, while
in Python, we use the def keyword. The function body in R is enclosed in
curly braces, while in Python it is indented.

There are a few differences in the syntax and functionality between the
two approaches:

Function arguments: In R, function arguments are separated by commas,
while in Python they are enclosed in parentheses. The syntax for
specifying default arguments and variable-length argument lists can also
differ between the two languages. Return statement: In R, we use the
return keyword to specify the return value of a function, while in
Python, we simply use the return statement. Function names: Function
names in R and Python can differ significantly. In the example above, we
used the sum_r() function in R and the sum_py() function in Python to
calculate the sum of two numbers.

## Data Plots

R Code:

``` r
# Load the "ggplot2" package for plotting
library(ggplot2)

# Generate some sample data
x <- seq(1, 10, 1)
y <- x + rnorm(10)

# Create a scatter plot
ggplot(data.frame(x, y), aes(x = x, y = y)) +
  geom_point()
```

![](bilingualism_md_files/figure-gfm/unnamed-chunk-25-1.pdf)<!-- -->
Python code:

``` python
# Load the "matplotlib" library
import matplotlib.pyplot as plt

# Generate some sample data
import numpy as np
x = np.arange(1, 11)
y = x + np.random.normal(0, 1, 10)

#clear last plot
plt.clf()

# Create a scatter plot
plt.scatter(x, y)
plt.show()
```

![](bilingualism_md_files/figure-gfm/unnamed-chunk-26-1.pdf)<!-- -->

In both cases, we generate some sample data and create a scatter plot to
visualize the relationship between the variables.

There are a few differences in the syntax and functionality between the
two approaches:

Library and package names: In R, we use the ggplot2 package for
plotting, while in Python, we use the matplotlib library. Data format:
In R, we use a data frame to store the input data, while in Python, we
use numpy arrays. Plotting functions: In R, we use the ggplot() function
to create a new plot object, and then use the geom_point() function to
create a scatter plot layer. In Python, we use the scatter() function
from the matplotlib.pyplot module to create a scatter plot directly.

## Linear regression

R Code:

``` r
# Load the "ggplot2" package for plotting
library(ggplot2)

# Generate some sample data
x <- seq(1, 10, 1)
y <- x + rnorm(10)

# Perform linear regression
model_r <- lm(y ~ x)

# Print the model summary
summary(model_r)
```

    ## 
    ## Call:
    ## lm(formula = y ~ x)
    ## 
    ## Residuals:
    ##      Min       1Q   Median       3Q      Max 
    ## -1.69344 -0.42336  0.08961  0.34778  1.56728 
    ## 
    ## Coefficients:
    ##             Estimate Std. Error t value Pr(>|t|)    
    ## (Intercept)  -0.1676     0.6781  -0.247    0.811    
    ## x             0.9750     0.1093   8.921 1.98e-05 ***
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Residual standard error: 0.9926 on 8 degrees of freedom
    ## Multiple R-squared:  0.9087, Adjusted R-squared:  0.8972 
    ## F-statistic: 79.59 on 1 and 8 DF,  p-value: 1.976e-05

``` r
# Plot the data and regression line
ggplot(data.frame(x, y), aes(x = x, y = y)) +
  geom_point() +
  geom_smooth(method = "lm", se = FALSE)
```

    ## `geom_smooth()` using formula = 'y ~ x'

![](bilingualism_md_files/figure-gfm/unnamed-chunk-27-3.pdf)<!-- -->

Python code:

``` python
# Load the "matplotlib" and "scikit-learn" libraries
import matplotlib.pyplot as plt
from sklearn.linear_model import LinearRegression

# Generate some sample data
import numpy as np
x = np.arange(1, 11)
y = x + np.random.normal(0, 1, 10)

# Perform linear regression
model_py = LinearRegression().fit(x.reshape(-1, 1), y)

# Print the model coefficients
print("Coefficients: ", model_py.coef_)
```

    ## Coefficients:  [1.15539692]

``` python
print("Intercept: ", model_py.intercept_)

#clear last plot
```

    ## Intercept:  -1.1291396173221218

``` python
plt.clf()

# Plot the data and regression line
plt.scatter(x, y)
plt.plot(x, model_py.predict(x.reshape(-1, 1)), color='red')
plt.show()
```

![](bilingualism_md_files/figure-gfm/unnamed-chunk-28-1.pdf)<!-- -->

In both cases, we generate some sample data with a linear relationship
between x and y, and then perform a simple linear regression to estimate
the slope and intercept of the line. We then plot the data and
regression line to visualize the fit.

There are a few differences in the syntax and functionality between the
two approaches:

Library and package names: In R, we use the lm() function from the base
package to perform linear regression, while in Python, we use the
LinearRegression() class from the scikit-learn library. Additionally, we
use the ggplot2 package in R for plotting, while we use the matplotlib
library in Python. Data format: In R, we can specify the dependent and
independent variables in the formula used for regression. In Python, we
need to reshape the input data to a two-dimensional array before fitting
the model. Model summary: In R, we can use the summary() function to
print a summary of the model, including the estimated coefficients,
standard errors, and p-values. In Python, we need to print the
coefficients and intercept separately.

## Random Forest

R Code:

``` r
# Load the "randomForest" package
library(randomForest)

# Load the "iris" dataset
data(iris)

# Split the data into training and testing sets
set.seed(123)
train_idx <- sample(1:nrow(iris), nrow(iris) * 0.7, replace = FALSE)
train_data <- iris[train_idx, ]
test_data <- iris[-train_idx, ]

# Build a random forest model
rf_model <- randomForest(Species ~ ., data = train_data, ntree = 500)

# Make predictions on the testing set
predictions <- predict(rf_model, test_data)

# Calculate accuracy of the model
accuracy <- sum(predictions == test_data$Species) / nrow(test_data)
print(paste("Accuracy:", accuracy))
```

    ## [1] "Accuracy: 0.977777777777778"

Python code:

``` python
# Load the "pandas", "numpy", and "sklearn" libraries
import pandas as pd
import numpy as np
from sklearn.ensemble import RandomForestClassifier
from sklearn.datasets import load_iris
from sklearn.model_selection import train_test_split

# Load the "iris" dataset
iris = load_iris()

# Split the data into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(iris.data, iris.target, test_size=0.3, random_state=123)

# Build a random forest model
rf_model = RandomForestClassifier(n_estimators=500, random_state=123)
rf_model.fit(X_train, y_train)

# Make predictions on the testing set
```

    ## RandomForestClassifier(n_estimators=500, random_state=123)

``` python
predictions = rf_model.predict(X_test)

# Calculate accuracy of the model
accuracy = sum(predictions == y_test) / len(y_test)
print("Accuracy:", accuracy)
```

    ## Accuracy: 0.9555555555555556

In both cases, we load the iris dataset and split it into training and
testing sets. We then build a random forest model using the training
data and evaluate its accuracy on the testing data.

There are a few differences in the syntax and functionality between the
two approaches:

Library and package names: In R, we use the randomForest package to
build random forest models, while in Python, we use the
RandomForestClassifier class from the sklearn.ensemble module. We also
use different libraries for loading and manipulating data (pandas and
numpy in Python, and built-in datasets in R). Model parameters: The
syntax for setting model parameters is slightly different in R and
Python. For example, in R, we specify the number of trees using the
ntree parameter, while in Python, we use the n_estimators parameter.
Data format: In R, we use a data frame to store the input data, while in
Python, we use numpy arrays.

## Basic streetmap from Open Street Map

R Code:

``` r
# Load the "osmdata" package for mapping
library(osmdata)
library(tmap)

# Define the map location and zoom level
bbox <- c(left = -0.16, bottom = 51.49, right = -0.13, top = 51.51)

# Get the OpenStreetMap data
osm_data <- opq(bbox) %>% 
  add_osm_feature(key = "highway") %>% 
  osmdata_sf()

# Plot the map using tmap
tm_shape(osm_data$osm_lines) + 
  tm_lines()
```

![](bilingualism_md_files/figure-gfm/unnamed-chunk-31-1.pdf)<!-- -->
Python code:

``` python
# Load the "osmnx" package for mapping
import osmnx as ox

# Define the map location and zoom level
bbox = (51.49, -0.16, 51.51, -0.13)

# Get the OpenStreetMap data
osm_data = ox.graph_from_bbox(north=bbox[2], south=bbox[0], east=bbox[3], west=bbox[1], network_type='all')

# Plot the map using osmnx
ox.plot_graph(osm_data)
```

    ## (<Figure size 1600x1600 with 0 Axes>, <AxesSubplot:>)

![](bilingualism_md_files/figure-gfm/unnamed-chunk-32-1.pdf)<!-- -->

In both cases, we define the map location and zoom level, retrieve the
OpenStreetMap data using the specified bounding box, and plot the map.

The main differences between the two approaches are:

Package names and syntax: In R, we use the osmdata package and its
syntax to download and process the OpenStreetMap data, while in Python,
we use the osmnx package and its syntax. Mapping libraries: In R, we use
the tmap package to create a static map of the OpenStreetMap data, while
in Python, we use the built-in ox.plot_graph function from the osmnx
package to plot the map.

## CNN on Raster data

R Code:

``` r
# Load the "keras" package for building the CNN
library(tensorflow)
library(keras)

# Load the "raster" package for working with raster data
library(raster)

# Load the "magrittr" package for pipe operator
library(magrittr)

# Load the data as a raster brick
raster_data <- brick("raster_data.tif")

# Split the data into training and testing sets
split_data <- sample(1:nlayers(raster_data), size = nlayers(raster_data)*0.8, replace = FALSE)
train_data <- raster_data[[split_data]]
test_data <- raster_data[[setdiff(1:nlayers(raster_data), split_data)]]

# Define the CNN model
model <- keras_model_sequential() %>% 
  layer_conv_2d(filters = 32, kernel_size = c(3, 3), activation = "relu", input_shape = c(ncol(train_data), nrow(train_data), ncell(train_data))) %>% 
  layer_max_pooling_2d(pool_size = c(2, 2)) %>% 
  layer_dropout(rate = 0.25) %>% 
  layer_flatten() %>% 
  layer_dense(units = 128, activation = "relu") %>% 
  layer_dropout(rate = 0.5) %>% 
  layer_dense(units = nlayers(train_data), activation = "softmax")

# Compile the model
model %>% compile(loss = "categorical_crossentropy", optimizer = "adam", metrics = "accuracy")

# Train the model
history <- model %>% fit(x = array(train_data), y = to_categorical(1:nlayers(train_data)), epochs = 10, validation_split = 0.2)

# Evaluate the model
model %>% evaluate(x = array(test_data), y = to_categorical(1:nlayers(test_data)))

# Plot the model accuracy over time
plot(history)
```

## Piping

Piping is a powerful feature in both R and Python that allows for a more
streamlined and readable code. However, the syntax for piping is
slightly different between the two languages.

In R, piping is done using the %\>% operator from the magrittr package,
while in Python, it is done using the \| operator from the pandas
package.

Let’s compare and contrast piping in R and Python with some examples:

Piping in R In R, we can use the %\>% operator to pipe output from one
function to another, which can make our code more readable and easier to
follow. Here’s an example:

R code:

``` r
library(dplyr)

# create a data frame
df <- data.frame(x = c(1,2,3), y = c(4,5,6))

# calculate the sum of column x and y
df %>%
  mutate(z = x + y) %>%
  summarize(sum_z = sum(z))
```

    ##   sum_z
    ## 1    21

In this example, we first create a data frame df with two columns x and
y. We then pipe the output of df to mutate, which adds a new column z to
the data frame that is the sum of x and y. Finally, we pipe the output
to summarize, which calculates the sum of z and returns the result.

Piping in Python In Python, we can use the \| operator to pipe output
from one function to another. However, instead of piping output from one
function to another, we pipe a DataFrame to a method of the DataFrame.
Here’s an example:

Python code:

``` python
import pandas as pd

# create a DataFrame
df = pd.DataFrame({'x': [1,2,3], 'y': [4,5,6]})

# calculate the sum of column x and y
(df.assign(z = df['x'] + df['y'])
   .agg(sum_z = ('z', 'sum')))
```

    ##         z
    ## sum_z  21

In this example, we first create a DataFrame df with two columns x and
y. We then use the assign() method to add a new column z to the
DataFrame that is the sum of x and y. Finally, we use the agg() method
to calculate the sum of z and return the result.

As we can see, the syntax for piping is slightly different between R and
Python, but the concept remains the same. Piping can make our code more
readable and easier to follow, which is an important aspect of creating
efficient and effective code.

R code:

``` r
library(dplyr)
library(ggplot2)

iris %>%
  filter(Species == "setosa") %>%
  group_by(Sepal.Width) %>%
  summarise(mean.Petal.Length = mean(Petal.Length)) %>%
  mutate(Sepal.Width = as.factor(Sepal.Width)) %>%
  ggplot(aes(x = Sepal.Width, y = mean.Petal.Length)) +
  geom_bar(stat = "identity", fill = "dodgerblue") +
  labs(title = "Mean Petal Length of Setosa by Sepal Width",
       x = "Sepal Width",
       y = "Mean Petal Length")
```

![](bilingualism_md_files/figure-gfm/unnamed-chunk-37-1.pdf)<!-- -->

In this example, we start with the iris dataset and filter it to only
include rows where the Species column is “setosa”. We then group the
remaining rows by the Sepal.Width column and calculate the mean
Petal.Length for each group. Next, we convert Sepal.Width to a factor
variable to ensure that it is treated as a categorical variable in the
visualization. Finally, we create a bar plot using ggplot2, with
Sepal.Width on the x-axis and mean.Petal.Length on the y-axis. The
resulting plot shows the mean petal length of setosa flowers for each
sepal width category.

Python code:

``` python
import pandas as pd

# Load the iris dataset and pipe it into the next function
( pd.read_csv("https://archive.ics.uci.edu/ml/machine-learning-databases/iris/iris.data", header=None, names=['sepal_length', 'sepal_width', 'petal_length', 'petal_width', 'class'])
  
  # Select columns and pivot the dataset
  .loc[:, ['sepal_length', 'sepal_width', 'petal_length']]
  .melt(var_name='variable', value_name='value')
  
  # Group by variable and calculate mean
  .groupby('variable', as_index=False)
  .mean()
  
  # Filter for mean greater than 3.5 and sort by descending mean
  .query('value > 3.5')
  .sort_values('value', ascending=False)
)
```

    ##        variable     value
    ## 1  sepal_length  5.843333
    ## 0  petal_length  3.758667

## for loops

Here is an example of a for loop in R:

R code

``` r
# Create a vector of numbers
numbers <- c(1, 2, 3, 4, 5)

# Use a for loop to print out each number in the vector
for (i in numbers) {
  print(i)
}
```

    ## [1] 1
    ## [1] 2
    ## [1] 3
    ## [1] 4
    ## [1] 5

In this example, the for loop iterates over each element in the numbers
vector, assigning the current element to the variable i. The print(i)
statement is then executed for each iteration, outputting the value of
i.

Here is the equivalent example in Python:

Python code

``` python
# Create a list of numbers
numbers = [1, 2, 3, 4, 5]

# Use a for loop to print out each number in the list
for i in numbers:
  print(i)
```

    ## 1
    ## 2
    ## 3
    ## 4
    ## 5

In Python, the for loop iterates over each element in the numbers list,
assigning the current element to the variable i. The print(i) statement
is then executed for each iteration, outputting the value of i.

Both languages also support nested for loops, which can be used to
perform iterations over multiple dimensions, such as looping through a
2D array.

## Parallel

Parallel computing is a technique used to execute multiple computational
tasks simultaneously, which can significantly reduce the time required
to complete a task. Both R and Python have built-in support for parallel
computing, although the approaches are slightly different. In this
answer, we will compare and contrast the parallel computing capabilities
of R and Python, and provide working examples in code.

Parallel computing in R In R, there are several packages that support
parallel computing, such as parallel, foreach, and doParallel. The
parallel package provides basic functionality for parallel computing,
while foreach and doParallel provide higher-level abstractions that make
it easier to write parallel code.

Here is an example of using the foreach package to execute a loop in
parallel:

R code:

``` r
library(foreach)
library(doParallel)

# Set up a parallel backend with 4 workers
cl <- makeCluster(4)
registerDoParallel(cl)

# Define a function to apply in parallel
myfunc <- function(x) {
  # some computation here
  return(x^2)
}

# Generate some data
mydata <- 1:1000

# Apply the function to the data in parallel
result <- foreach(i = mydata) %dopar% {
  myfunc(i)
}

# Stop the cluster
stopCluster(cl)
```

In this example, we use the makeCluster() function to set up a cluster
with 4 workers, and the registerDoParallel() function to register the
cluster as the parallel backend for foreach. We then define a function
myfunc() that takes an input x and returns x^2. We generate some data
mydata and use foreach to apply myfunc() to each element of mydata in
parallel, using the %dopar% operator.

R Tidyverse parallel

In R Tidyverse, we can use the furrr package for parallel computing.
Here’s an example of using furrr to parallelize a map function:

R Tidy code:

``` r
library(tidyverse)
library(furrr)

# Generate a list of numbers
numbers <- 1:10

# Use the future_map function from furrr to parallelize the map function
plan(multisession)
squares <- future_map(numbers, function(x) x^2)
```

In this example, we first load the Tidyverse and furrr libraries. We
then generate a list of numbers from 1 to 10. We then use the plan
function to set the parallelization strategy to “multisession”, which
will use multiple CPU cores to execute the code. Finally, we use the
future_map function from furrr to apply the function x^2 to each number
in the list in parallel.

Parallel computing in Python In Python, the standard library includes
the multiprocessing module, which provides basic support for parallel
computing. Additionally, there are several third-party packages that
provide higher-level abstractions, such as joblib and dask.

Here is an example of using the multiprocessing module to execute a loop
in parallel:

Python code:

``` python
def square(x):
    return x**2
  
from multiprocessing import Pool

# Generate a list of numbers
numbers = list(range(1, 11))

# Use the map function and a pool of workers to parallelize the square function
with Pool() as pool:
    squares = pool.map(square, numbers)
    
print(squares)
```

In this example, we define a function myfunc() that takes an input x and
returns x^2. We generate some data mydata and use the Pool class from
the multiprocessing module to set up a pool of 4 workers. We then use
the map() method of the Pool class to apply myfunc() to each element of
mydata in parallel.

Comparison and contrast Both R and Python have built-in support for
parallel computing, with similar basic functionality for creating and
managing parallel processes. However, the higher-level abstractions
differ between the two languages. In R, the foreach package provides a
high-level interface that makes it easy to write parallel code, while in
Python, the multiprocessing module provides a basic interface that can
be extended using third-party packages like joblib and dask.

Additionally, Python has better support for distributed computing using
frameworks like Apache Spark, while R has better support for
shared-memory parallelism using tools like data.table and ff.

## Data wrangling

Data wrangling is an important part of any data analysis project, and
both R and Python provide tools and libraries for performing this task.
In this answer, we will compare and contrast data wrangling in R’s
tidyverse and Python’s pandas library, with working examples in code.

Data Wrangling in R Tidyverse

The tidyverse is a collection of R packages designed for data science,
and it includes several packages that are useful for data wrangling. One
of the most popular packages is dplyr, which provides a grammar of data
manipulation for data frames.

Here is an example of using dplyr to filter, mutate, and summarize a
data frame:

R code

``` r
library(dplyr)

# Load data
data(mtcars)

# Filter for cars with more than 100 horsepower
mtcars %>%
  filter(hp > 100) %>%
  # Add a new column with fuel efficiency in km per liter
  mutate(kmpl = 0.425 * mpg) %>%
  # Group by number of cylinders and summarize
  group_by(cyl) %>%
  summarize(mean_hp = mean(hp),
            mean_kmpl = mean(kmpl))
```

    ## # A tibble: 3 × 3
    ##     cyl mean_hp mean_kmpl
    ##   <dbl>   <dbl>     <dbl>
    ## 1     4    111      11.0 
    ## 2     6    122.      8.39
    ## 3     8    209.      6.42

In this example, we first filter the mtcars data frame to only include
cars with more than 100 horsepower. We then use mutate to create a new
column with fuel efficiency in kilometers per liter. Finally, we group
the data by the number of cylinders and calculate the mean horsepower
and fuel efficiency.

Data Wrangling in Python Pandas

Pandas is a popular library for data manipulation in Python. It provides
a data frame object similar to R’s data frames, along with a wide range
of functions for data wrangling.

Here is an example of using pandas to filter, transform, and group a
data frame:

Python code:

``` python
import pandas as pd

# Load data
mtcars = pd.read_csv('https://raw.githubusercontent.com/mwaskom/seaborn-data/master/mtcars.csv')

# Filter for cars with more than 100 horsepower
filtered_mtcars = mtcars[mtcars['hp'] > 100]

# Add a new column with fuel efficiency in km per liter
filtered_mtcars['kmpl'] = 0.425 * filtered_mtcars['mpg']

# Group by number of cylinders and calculate mean horsepower and fuel efficiency
grouped_mtcars = filtered_mtcars.groupby('cyl').agg({'hp': 'mean',
                                                     'kmpl': 'mean'})
```

In this example, we first load the mtcars data from a CSV file. We then
filter the data to only include cars with more than 100 horsepower,
using boolean indexing. We use the assign function to create a new
column with fuel efficiency in kilometers per liter. Finally, we group
the data by the number of cylinders and calculate the mean horsepower
and fuel efficiency.

Comparison

Overall, both R’s tidyverse and Python’s pandas provide similar
functionality for data wrangling. Both allow for filtering,
transforming, and aggregating data frames. The syntax for performing
these operations is slightly different between the two languages, with R
using the %\>% operator for chaining operations and Python using method
chaining or the apply family of functions.

One key difference between the two languages is that R’s tidyverse
provides a consistent grammar for data manipulation across its various
packages, making it easier to learn and use. However, Python’s pandas
library has a larger developer community and is more versatile for use
in other applications, such as web development or machine learning.

In conclusion, both R and Python provide powerful tools for data
wrangling, and the choice between the two ultimately depends on the
specific needs of the user and their familiarity

## Data from API

Retrieving data from an API is a common task in both R and Python. Here
are examples of how to retrieve data from an API in both languages:

Python

To retrieve data from an API in Python, we can use the requests library.
Here’s an example of how to retrieve weather data from the
OpenWeatherMap API:

Python code:

``` python
import requests

url = 'https://api.openweathermap.org/data/2.5/weather?q=London,uk&appid=API_KEY'

response = requests.get(url)

data = response.json()

print(data)
```

This code retrieves the current weather data for London from the
OpenWeatherMap API. We first construct the API URL with the location and
API key, then use the requests.get() function to make a request to the
API. We then extract the JSON data from the response using the .json()
method and print the resulting data.

R

In R, we can use the httr package to retrieve data from an API. Here’s
an example of how to retrieve weather data from the OpenWeatherMap API
in R:

R code:

``` r
library(httr)

url <- 'https://api.openweathermap.org/data/2.5/weather?q=London,uk&appid=API_KEY'

response <- GET(url)

data <- content(response, 'text')

print(data)
```

This code is similar to the Python code above. We first load the httr
library, then construct the API URL and use the GET() function to make a
request to the API. We then extract the data from the response using the
content() function and print the resulting data.

Retrieving Data from an API in R Tidyverse In R Tidyverse, we can use
the httr and jsonlite packages to retrieve and process data from an API.

R code:

``` r
# Load required packages
library(httr)
library(jsonlite)

# Define API endpoint
endpoint <- "https://jsonplaceholder.typicode.com/posts"

# Retrieve data from API
response <- GET(endpoint)

# Extract content from response
content <- content(response, "text")

# Convert content to JSON
json <- fromJSON(content)

# Convert JSON to a data frame
df <- as.data.frame(json)
```

In the above example, we use the GET() function from the httr package to
retrieve data from an API endpoint, and the content() function to
extract the content of the response. We then use the fromJSON() function
from the jsonlite package to convert the JSON content to a list, and the
as.data.frame() function to convert the list to a data frame.

Retrieving Data from an API in Python In Python, we can use the requests
library to retrieve data from an API, and the json library to process
the JSON data.

Python code:

``` python
# Load required libraries
import requests
import json

# Define API endpoint
endpoint = "https://jsonplaceholder.typicode.com/posts"

# Retrieve data from API
response = requests.get(endpoint)

# Extract content from response
content = response.content

# Convert content to JSON
json_data = json.loads(content)

# Convert JSON to a list of dictionaries
data = [dict(row) for row in json_data]
```

In the above example, we use the get() function from the requests
library to retrieve data from an API endpoint, and the content attribute
to extract the content of the response. We then use the loads() function
from the json library to convert the JSON content to a list of
dictionaries.

Comparison Both R Tidyverse and Python provide powerful tools for
retrieving and processing data from an API. In terms of syntax, the two
languages are somewhat similar. In both cases, we use a library to
retrieve data from the API, extract the content of the response, and
then process the JSON data. However, there are some differences in the
specific functions and methods used. For example, in R Tidyverse, we use
the content() function to extract the content of the response, whereas
in Python, we use the content attribute. Additionally, in R Tidyverse,
we use the fromJSON() function to convert the JSON data to a list,
whereas in Python, we use the loads() function.

## Census data

Retrieving USA census data in R, R Tidy, and Python can be done using
different packages and libraries. Here are some working examples in code
for each language:

R:

To retrieve census data in R, we can use the tidycensus package. Here’s
an example of how to retrieve the total population for the state of
California:

R code:

``` r
library(tidycensus)
library(tidyverse)

# Set your Census API key
census_api_key("your_api_key")

# Get the total population for the state of California
ca_pop <- get_acs(
  geography = "state",
  variables = "B01003_001",
  state = "CA"
) %>% 
  rename(total_population = estimate) %>% 
  select(total_population)

# View the result
ca_pop
```

R Tidy:

To retrieve census data in R Tidy, we can also use the tidycensus
package. Here’s an example of how to retrieve the total population for
the state of California using pipes and dplyr functions:

R tidy code:

``` r
library(tidycensus)
library(tidyverse)

# Set your Census API key
census_api_key("your_api_key")

# Get the total population for the state of California
ca_pop <- get_acs(
  geography = "state",
  variables = "B01003_001",
  state = "CA"
) %>% 
  rename(total_population = estimate) %>% 
  select(total_population)

# View the result
ca_pop
```

Python:

To retrieve census data in Python, we can use the census library. Here’s
an example of how to retrieve the total population for the state of
California:

Python code:

``` python
from census import Census
from us import states
import pandas as pd

# Set your Census API key
c = Census("your_api_key")

# Get the total population for the state of California
ca_pop = c.acs5.state(("B01003_001"), states.CA.fips, year=2019)

# Convert the result to a Pandas DataFrame
ca_pop_df = pd.DataFrame(ca_pop)

# Rename the column
ca_pop_df = ca_pop_df.rename(columns={"B01003_001E": "total_population"})

# Select only the total population column
ca_pop_df = ca_pop_df[["total_population"]]

# View the result
ca_pop_df
```

## Lidar data

To find Lidar data in R and Python, you typically need to start by
identifying sources of Lidar data and then accessing them using
appropriate packages and functions. Here are some examples of how to
find Lidar data in R and Python:

R:

Identify sources of Lidar data: The USGS National Map Viewer provides
access to Lidar data for the United States. You can also find Lidar data
on state and local government websites, as well as on commercial data
providers’ websites. Access the data: You can use the lidR package in R
to download and read Lidar data in the LAS format. For example, the
following code downloads and reads Lidar data for a specific area:

R code:

``` r
library(lidR)

# Download Lidar data
LASfile <- system.file("extdata", "Megaplot.laz", package="lidR")
lidar <- readLAS(LASfile)

# Visualize the data
plot(lidar)
```

Python:

Identify sources of Lidar data: The USGS 3DEP program provides access to
Lidar data for the United States. You can also find Lidar data on state
and local government websites, as well as on commercial data providers’
websites. Access the data: You can use the pylastools package in Python
to download and read Lidar data in the LAS format. For example, the
following code downloads and reads Lidar data for a specific area:

Python code:

``` r
py_install("requests")
py_install("pylas")
py_install("laspy")
```

``` python
import requests
from pylas import read
import laspy
import numpy as np

# Download Lidar data
url = "https://s3-us-west-2.amazonaws.com/usgs-lidar-public/USGS_LPC_CA_SanFrancisco_2016_LAS_2018.zip"
lasfile = "USGS_LPC_CA_SanFrancisco_2016_LAS_2018.las"
r = requests.get(url, allow_redirects=True)
open(lasfile, 'wb').write(r.content)

# Read the data
lidar = read(lasfile)

# Visualize the data
laspy.plot.plot(lidar)
```

## Data for black lives

Data for Black Lives (<https://d4bl.org/>) is a movement that uses data
science to create measurable change in the lives of Black people. While
the Data for Black Lives website provides resources, reports, articles,
and datasets related to racial equity, it doesn’t provide a direct API
for downloading data.

Instead, you can access the Data for Black Lives GitHub repository
(<https://github.com/Data4BlackLives>) to find datasets and resources to
work with. In this example, we’ll use a sample dataset available at
<https://github.com/Data4BlackLives/covid-19/tree/master/data>. The
dataset “COVID19_race_data.csv” contains COVID-19 race-related data.

R: In R, we’ll use the ‘readr’ and ‘dplyr’ packages to read, process,
and analyze the dataset.

R code:

``` r
# Install and load necessary libraries

library(readr)
library(dplyr)

# Read the CSV file
url <- "https://raw.githubusercontent.com/Data4BlackLives/covid-19/master/data/COVID19_race_data.csv"
data <- read_csv(url)

# Basic information about the dataset
print(dim(data))
print(head(data))

# Example analysis: calculate the mean of 'cases_total' by 'state'
data %>%
  group_by(state) %>%
  summarize(mean_cases_total = mean(cases_total, na.rm = TRUE)) %>%
  arrange(desc(mean_cases_total))
```

Python: In Python, we’ll use the ‘pandas’ library to read, process, and
analyze the dataset.

Python code:

``` python
import pandas as pd

# Read the CSV file
url = "https://raw.githubusercontent.com/Data4BlackLives/covid-19/master/data/COVID19_race_data.csv"
data = pd.read_csv(url)

# Basic information about the dataset
print(data.shape)
print(data.head())

# Example analysis: calculate the mean of 'cases_total' by 'state'
mean_cases_total = data.groupby("state")["cases_total"].mean().sort_values(ascending=False)
print(mean_cases_total)
```

In conclusion, both R and Python provide powerful libraries and tools
for downloading, processing, and analyzing datasets, such as those found
in the Data for Black Lives repository. The ‘readr’ and ‘dplyr’
libraries in R offer a simple and intuitive way to read and manipulate
data, while the ‘pandas’ library in Python offers similar functionality
with a different syntax. Depending on your preferred programming
language and environment, both options can be effective in working with
social justice datasets.

## Propublica Congress API

The ProPublica Congress API provides information about the U.S. Congress
members and their voting records. In this example, we’ll fetch data
about the current Senate members and calculate the number of members in
each party.

R: In R, we’ll use the ‘httr’ and ‘jsonlite’ packages to fetch and
process data from the ProPublica Congress API.

R code:

``` r
# load necessary libraries
library(httr)
library(jsonlite)

# Replace 'your_api_key' with your ProPublica API key

#

# Fetch data about the current Senate members
url <- "https://api.propublica.org/congress/v1/117/senate/members.json"
response <- GET(url, add_headers(`X-API-Key` = api_key))

# Check if the request was successful
if (http_status(response)$category == "Success") {
  data <- content(response, "parsed")
  members <- data$results[[1]]$members
  
  # Calculate the number of members in each party
  party_counts <- table(sapply(members, function(x) x$party))
  print(party_counts)
} else {
  print(http_status(response)$message)
}
```

    ## 
    ##  D  I ID  R 
    ## 49  1  2 51

Python: In Python, we’ll use the ‘requests’ library to fetch data from
the ProPublica Congress API and ‘pandas’ library to process the data.

python code:

``` python
# Install necessary libraries

import requests
import pandas as pd

# Replace 'your_api_key' with your ProPublica API key
api_key = "your_api_key"
headers = {"X-API-Key": api_key}

# Fetch data about the current Senate members
url = "https://api.propublica.org/congress/v1/117/senate/members.json"
response = requests.get(url, headers=headers)

# Check if the request was successful
if response.status_code == 200:
    data = response.json()
    members = data["results"][0]["members"]
    
    # Calculate the number of members in each party
    party_counts = pd.DataFrame(members)["party"].value_counts()
    print(party_counts)
else:
    print(f"Error: {response.status_code}")
```

In conclusion, both R and Python offer efficient ways to fetch and
process data from APIs like the ProPublica Congress API. The ‘httr’ and
‘jsonlite’ libraries in R provide a straightforward way to make HTTP
requests and parse JSON data, while the ‘requests’ library in Python
offers similar functionality. The ‘pandas’ library in Python can be used
for data manipulation and analysis, and R provides built-in functions
like table() for aggregating data. Depending on your preferred
programming language and environment, both options can be effective for
working with the ProPublica Congress API.

## Nonprofit Explorer API by ProPublica

The Nonprofit Explorer API by ProPublica provides data on tax-exempt
organizations in the United States. In this example, we’ll search for
organizations with the keyword “education” and analyze the results.

R: In R, we’ll use the ‘httr’ and ‘jsonlite’ packages to fetch and
process data from the Nonprofit Explorer API.

R code:

``` r
# Install and load necessary libraries
library(httr)
library(jsonlite)

# Fetch data for organizations with the keyword "education"
url <- "https://projects.propublica.org/nonprofits/api/v2/search.json?q=education"
response <- GET(url)

# Check if the request was successful
if (http_status(response)$category == "Success") {
  data <- content(response, "parsed")
  organizations <- data$organizations
  
  # Count the number of organizations per state
  state_counts <- table(sapply(organizations, function(x) x$state))
  print(state_counts)
} else {
  print(http_status(response)$message)
}
```

    ## 
    ##      AZ      CA      CO      DC      FL      GA      HI      IL Indiana      LA 
    ##       3      22       6       5       3       2       1       2       1       1 
    ##      MD      MI      MN      MO      MP      MS      NC      NE      NJ      NM 
    ##       1       2       5       3       1       1       2       2       2       1 
    ##      NY      OH      OK  Oregon      PA      TX      UT      VA      WA      WV 
    ##       1       5       1       2       2      12       1       4       3       1 
    ##      ZZ 
    ##       2

Python: In Python, we’ll use the ‘requests’ library to fetch data from
the Nonprofit Explorer API and ‘pandas’ library to process the data.

Python code:

``` python
# Install necessary libraries
import requests
import pandas as pd

# Fetch data for organizations with the keyword "education"
url = "https://projects.propublica.org/nonprofits/api/v2/search.json?q=education"
response = requests.get(url)

# Check if the request was successful
if response.status_code == 200:
    data = response.json()
    organizations = data["organizations"]
    
    # Count the number of organizations per state
    state_counts = pd.DataFrame(organizations)["state"].value_counts()
    print(state_counts)
else:
    print(f"Error: {response.status_code}")
```

    ## CA         22
    ## TX         12
    ## CO          6
    ## MN          5
    ## OH          5
    ## DC          5
    ## VA          4
    ## AZ          3
    ## WA          3
    ## MO          3
    ## FL          3
    ## IL          2
    ## GA          2
    ## NC          2
    ## MI          2
    ## Oregon      2
    ## NE          2
    ## ZZ          2
    ## PA          2
    ## NJ          2
    ## HI          1
    ## MS          1
    ## NY          1
    ## Indiana     1
    ## NM          1
    ## LA          1
    ## UT          1
    ## MD          1
    ## MP          1
    ## WV          1
    ## OK          1
    ## Name: state, dtype: int64

In conclusion, both R and Python offer efficient ways to fetch and
process data from APIs like the Nonprofit Explorer API. The ‘httr’ and
‘jsonlite’ libraries in R provide a straightforward way to make HTTP
requests and parse JSON data, while the ‘requests’ library in Python
offers similar functionality. The ‘pandas’ library in Python can be used
for data manipulation and analysis, and R provides built-in functions
like table() for aggregating data. Depending on your preferred
programming language and environment, both options can be effective for
working with the Nonprofit Explorer API.

## Campaign Finance API by ProPublica

The Campaign Finance API by the Federal Election Commission (FEC)
provides data on campaign finance in U.S. federal elections. In this
example, we’ll fetch data about individual contributions for the 2020
election cycle and analyze the results.

R: In R, we’ll use the ‘httr’ and ‘jsonlite’ packages to fetch and
process data from the Campaign Finance API.

R code:

``` r
# Install and load necessary libraries
library(httr)
library(jsonlite)

# Fetch data about individual contributions for the 2020 election cycle
url <- "https://api.open.fec.gov/v1/schedules/schedule_a/?api_key='OGwpkX7tH5Jihs1qQcisKfVAMddJzmzouWKtKoby'&two_year_transaction_period=2020&sort_hide_null=false&sort_null_only=false&per_page=20&page=1"
response <- GET(url)

# Check if the request was successful
if (http_status(response)$category == "Success") {
  data <- content(response, "parsed")
  contributions <- data$results
  
  # Calculate the total contributions per state
  state_totals <- aggregate(contributions$contributor_state, by = list(contributions$contributor_state), FUN = sum)
  colnames(state_totals) <- c("State", "Total_Contributions")
  print(state_totals)
} else {
  print(http_status(response)$message)
}
```

    ## [1] "Client error: (403) Forbidden"

Python: In Python, we’ll use the ‘requests’ library to fetch data from
the Campaign Finance API and ‘pandas’ library to process the data.

Python code:

``` python
# Install necessary libraries

import requests
import pandas as pd

# Fetch data about individual contributions for the 2020 election cycle
url = "https://api.open.fec.gov/v1/schedules/schedule_a/?api_key=your_api_key&two_year_transaction_period=2020&sort_hide_null=false&sort_null_only=false&per_page=20&page=1"
response = requests.get(url)

# Check if the request was successful
if response.status_code == 200:
    data = response.json()
    contributions = data["results"]
    
    # Calculate the total contributions per state
    df = pd.DataFrame(contributions)
    state_totals = df.groupby("contributor_state")["contribution_receipt_amount"].sum()
    print(state_totals)
else:
    print(f"Error: {response.status_code}")
```

    ## Error: 403

In conclusion, both R and Python offer efficient ways to fetch and
process data from APIs like the Campaign Finance API. The ‘httr’ and
‘jsonlite’ libraries in R provide a straightforward way to make HTTP
requests and parse JSON data, while the ‘requests’ library in Python
offers similar functionality. The ‘pandas’ library in Python can be used
for data manipulation and analysis, and R provides built-in functions
like aggregate() for aggregating data. Depending on your preferred
programming language and environment, both options can be effective for
working with the Campaign Finance API.

Note: Remember to replace your_api_key with your actual FEC API key in
the code examples above.

## Historic Redlining

Historic redlining data refers to data from the Home Owners’ Loan
Corporation (HOLC) that created residential security maps in the 1930s,
which contributed to racial segregation and disinvestment in minority
neighborhoods. One popular source for this data is the Mapping
Inequality project (<https://dsl.richmond.edu/panorama/redlining/>).

In this example, we’ll download historic redlining data for Philadelphia
in the form of a GeoJSON file and analyze the data in R and Python.

R: In R, we’ll use the ‘sf’ and ‘dplyr’ packages to read and process the
GeoJSON data.

R code:

``` r
# Install and load necessary libraries
library(sf)
library(dplyr)

# Download historic redlining data for Philadelphia
url <- "https://dsl.richmond.edu/panorama/redlining/static/downloads/geojson/PAPhiladelphia1937.geojson"
philly_geojson <- read_sf(url)

# Count the number of areas per HOLC grade
grade_counts <- philly_geojson %>%
  group_by(holc_grade) %>%
  summarize(count = n())

plot(grade_counts)
```

![](bilingualism_md_files/figure-gfm/unnamed-chunk-65-1.pdf)<!-- -->

Python: In Python, we’ll use the ‘geopandas’ library to read and process
the GeoJSON data.

Python code:

``` python
# Install necessary libraries


import geopandas as gpd

# Download historic redlining data for Philadelphia
url = "https://dsl.richmond.edu/panorama/redlining/static/downloads/geojson/PAPhiladelphia1937.geojson"
philly_geojson = gpd.read_file(url)

# Count the number of areas per HOLC grade
grade_counts = philly_geojson["holc_grade"].value_counts()
print(grade_counts)
```

    ## B    28
    ## D    26
    ## C    18
    ## A    10
    ## Name: holc_grade, dtype: int64

In conclusion, both R and Python offer efficient ways to download and
process historic redlining data in the form of GeoJSON files. The ‘sf’
package in R provides a simple way to read and manipulate spatial data,
while the ‘geopandas’ library in Python offers similar functionality.
The ‘dplyr’ package in R can be used for data manipulation and analysis,
and Python’s built-in functions like value_counts() can be used for
aggregating data. Depending on your preferred programming language and
environment, both options can be effective for working with historic
redlining data.

## American Indian and Alaska Native Areas (AIANNH)

In this example, we’ll download and analyze the American Indian and
Alaska Native Areas (AIANNH) TIGER/Line Shapefile from the U.S. Census
Bureau. We’ll download the data for the year 2020, and analyze the
number of AIANNH per congressional district

R: In R, we’ll use the ‘sf’ and ‘dplyr’ packages to read and process the
Shapefile data.

R code:

``` r
# Install and load necessary libraries
library(sf)
library(dplyr)

# Download historic redlining data for Philadelphia
url <- "https://www2.census.gov/geo/tiger/TIGER2020/AIANNH/tl_2020_us_aiannh.zip"
temp_file <- tempfile(fileext = ".zip")
download.file(url, temp_file, mode = "wb")
unzip(temp_file, exdir = tempdir())

# Read the Shapefile
shapefile_path <- file.path(tempdir(), "tl_2020_us_aiannh.shp")
aiannh <- read_sf(shapefile_path)

# Count the number of AIANNH per congressional district
state_counts <- aiannh %>%
  group_by(LSAD) %>%
  summarize(count = n())

print(state_counts[order(-state_counts$count),])
```

    ## Simple feature collection with 26 features and 2 fields
    ## Geometry type: GEOMETRY
    ## Dimension:     XY
    ## Bounding box:  xmin: -174.236 ymin: 18.91069 xmax: -67.03552 ymax: 71.34019
    ## Geodetic CRS:  NAD83
    ## # A tibble: 26 × 3
    ##    LSAD  count                                                          geometry
    ##    <chr> <int>                                                <MULTIPOLYGON [°]>
    ##  1 79      221 (((-166.5331 65.33918, -166.5331 65.33906, -166.533 65.33699, -1…
    ##  2 86      206 (((-83.38811 35.46645, -83.38342 35.46596, -83.38316 35.46593, -…
    ##  3 OT      155 (((-92.32972 47.81374, -92.3297 47.81305, -92.32967 47.81196, -9…
    ##  4 78       75 (((-155.729 20.02457, -155.7288 20.02428, -155.7288 20.02427, -1…
    ##  5 85       46 (((-122.3355 37.95215, -122.3354 37.95206, -122.3352 37.95199, -…
    ##  6 92       35 (((-93.01356 31.56287, -93.01354 31.56251, -93.01316 31.56019, -…
    ##  7 88       25 (((-97.35299 36.908, -97.35291 36.90801, -97.35287 36.908, -97.3…
    ##  8 96       19 (((-116.48 32.63814, -116.48 32.63718, -116.4794 32.63716, -116.…
    ##  9 84       16 (((-105.5937 36.40379, -105.5937 36.40324, -105.5937 36.40251, -…
    ## 10 89       11 (((-95.91705 41.28037, -95.91653 41.28036, -95.91653 41.28125, -…
    ## # ℹ 16 more rows

Python: In Python, we’ll use the ‘geopandas’ library to read and process
the Shapefile data.

Python code:

``` python
import geopandas as gpd
import pandas as pd
import requests
import zipfile
import os
from io import BytesIO

# Download historic redlining data for Philadelphia
url = "https://www2.census.gov/geo/tiger/TIGER2020/AIANNH/tl_2020_us_aiannh.zip"
response = requests.get(url)
zip_file = zipfile.ZipFile(BytesIO(response.content))

# Extract Shapefile
temp_dir = "temp"
if not os.path.exists(temp_dir):
    os.makedirs(temp_dir)

zip_file.extractall(path=temp_dir)
shapefile_path = os.path.join(temp_dir, "tl_2020_us_aiannh.shp")

# Read the Shapefile
aiannh = gpd.read_file(shapefile_path)

# Count the number of AIANNH per congressional district
state_counts = aiannh.groupby("LSAD").size().reset_index(name="count")

# Sort by descending count
state_counts_sorted = state_counts.sort_values(by="count", ascending=False)

print(state_counts_sorted)
```

    ##    LSAD  count
    ## 2    79    221
    ## 9    86    206
    ## 25   OT    155
    ## 1    78     75
    ## 8    85     46
    ## 15   92     35
    ## 11   88     25
    ## 19   96     19
    ## 7    84     16
    ## 12   89     11
    ## 5    82      8
    ## 3    80      7
    ## 4    81      6
    ## 21   98      5
    ## 20   97      5
    ## 13   90      4
    ## 18   95      3
    ## 6    83      3
    ## 17   94      2
    ## 16   93      1
    ## 14   91      1
    ## 10   87      1
    ## 22   99      1
    ## 23   9C      1
    ## 24   9D      1
    ## 0    00      1

In conclusion, both R and Python offer efficient ways to download and
process AIANNH TIGER/Line Shapefile data from the U.S. Census Bureau.
The ‘sf’ package in R provides a simple way to read and manipulate
spatial data, while the ‘geopandas’ library in Python offers similar
functionality. The ‘dplyr’ package in R can be used for data
manipulation and analysis, and Python’s built-in functions like
value_counts() can be used for aggregating data. Depending on your
preferred programming language and environment, both options can be
effective for working with AIANNH data.

## Indian Entities Recognized and Eligible To Receive Services by BIA

The Bureau of Indian Affairs (BIA) provides a PDF document containing a
list of Indian Entities Recognized and Eligible To Receive Services. To
analyze the data, we’ll first need to extract the information from the
PDF. In this example, we’ll extract the names of the recognized tribes
and count the number of tribes per state.

R: In R, we’ll use the ‘pdftools’ package to extract text from the PDF
and the ‘stringr’ package to process the text data.

R code:

``` r
# Install and load necessary libraries
library(pdftools)
library(stringr)
library(dplyr)

# Download the BIA PDF
url <- "https://www.govinfo.gov/content/pkg/FR-2022-01-28/pdf/2022-01789.pdf"
temp_file <- tempfile(fileext = ".pdf")
download.file(url, temp_file, mode = "wb")

# Extract text from the PDF
pdf_text <- pdf_text(temp_file)
tribe_text <- pdf_text[4:length(pdf_text)]

# Define helper functions
tribe_state_extractor <- function(text_line) {
  regex_pattern <- "(.*),\\s+([A-Z]{2})$"
  tribe_state <- str_match(text_line, regex_pattern)
  return(tribe_state)
}

is_valid_tribe_line <- function(text_line) {
  regex_pattern <- "^\\d+\\s+"
  return(!is.na(str_match(text_line, regex_pattern)))
}

# Process text data to extract tribes and states
tribe_states <- sapply(tribe_text, tribe_state_extractor)
valid_lines <- sapply(tribe_text, is_valid_tribe_line)
tribe_states <- tribe_states[valid_lines, 2:3]

# Count the number of tribes per state
tribe_data <- as.data.frame(tribe_states)
colnames(tribe_data) <- c("Tribe", "State")
state_counts <- tribe_data %>%
  group_by(State) %>%
  summarise(Count = n())

print(state_counts)
```

    ## # A tibble: 0 × 2
    ## # ℹ 2 variables: State <chr>, Count <int>

Python: In Python, we’ll use the ‘PyPDF2’ library to extract text from
the PDF and the ‘re’ module to process the text data.

Python code:

``` python
# Install necessary libraries
import requests
import PyPDF2
import io
import re
from collections import Counter

# Download the BIA PDF
url = "https://www.bia.gov/sites/bia.gov/files/assets/public/raca/online-tribal-leaders-directory/tribal_leaders_2021-12-27.pdf"
response = requests.get(url)

# Extract text from the PDF
pdf_reader = PyPDF2.PdfFileReader(io.BytesIO(response.content))
tribe_text = [pdf_reader.getPage(i).extractText() for i in range(3, pdf_reader.numPages)]

# Process text data to extract tribes and states
tribes = [re.findall(r'^\d+\s+(.+),\s+([A-Z]{2})', line) for text in tribe_text for line in text.split('\n') if line]
tribe_states = [state for tribe, state in tribes]

# Count the number of tribes per state
state_counts = Counter(tribe_states)
print(state_counts)
```

In conclusion, both R and Python offer efficient ways to download and
process the list of Indian Entities Recognized and Eligible To Receive
Services from the BIA. The ‘pdftools’ package in R provides a simple way
to extract text from PDF files, while the ‘PyPDF2’ library in Python
offers similar functionality. The ‘stringr’ package in R and the ‘re’
module in Python can be used to process and analyze text data. Depending
on your preferred programming language and environment, both options can
be effective for working with BIA data.

## National Atlas - Indian Lands of the United States dataset

In this example, we will download and analyze the National Atlas -
Indian Lands of the United States dataset in both R and Python. We will
read the dataset and count the number of Indian lands per state.

R: In R, we’ll use the ‘sf’ package to read the Shapefile and the
‘dplyr’ package to process the data.

R code:

``` r
# Install and load necessary libraries

library(sf)
library(dplyr)

# Download the Indian Lands dataset
url <- "https://prd-tnm.s3.amazonaws.com/StagedProducts/Small-scale/data/Boundaries/indlanp010g.shp_nt00968.tar.gz"
temp_file <- tempfile(fileext = ".tar.gz")
download.file(url, temp_file, mode = "wb")
untar(temp_file, exdir = tempdir())

# Read the Shapefile
shapefile_path <- file.path(tempdir(), "indlanp010g.shp")
indian_lands <- read_sf(shapefile_path)

# Count the number of Indian lands per state
# state_counts <- indian_lands %>%
#   group_by(STATE) %>%
#   summarize(count = n())

plot(indian_lands)
```

    ## Warning: plotting the first 9 out of 23 attributes; use max.plot = 23 to plot
    ## all

![](bilingualism_md_files/figure-gfm/unnamed-chunk-71-1.pdf)<!-- -->

Python: In Python, we’ll use the ‘geopandas’ and ‘pandas’ libraries to
read the Shapefile and process the data.

Python code:

``` python
import geopandas as gpd
import pandas as pd
import requests
import tarfile
import os
from io import BytesIO

# Download the Indian Lands dataset
url = "https://prd-tnm.s3.amazonaws.com/StagedProducts/Small-scale/data/Boundaries/indlanp010g.shp_nt00966.tar.gz"
response = requests.get(url)
tar_file = tarfile.open(fileobj=BytesIO(response.content), mode='r:gz')

# Extract Shapefile
temp_dir = "temp"
if not os.path.exists(temp_dir):
    os.makedirs(temp_dir)

tar_file.extractall(path=temp_dir)
shapefile_path = os.path.join(temp_dir, "indlanp010g.shp")

# Read the Shapefile
indian_lands = gpd.read_file(shapefile_path)

# Count the number of Indian lands per state
state_counts = indian_lands.groupby("STATE").size().reset_index(name="count")

print(state_counts)
```

Both R and Python codes download the dataset and read the Shapefile
using the respective packages. They then group the data by the ‘STATE’
attribute and calculate the count of Indian lands per state.
