Keep only first row for each unique value of a column

```
dataframe[!duplicated(dataframe$column),]
```

Remove columns that have no variation

```
Filter(function(x) sd(x) != 0, dataframe)
```

Install all R packages from a folder

```
setwd("path/packages/") #set the working directory to the path of the packages
pkgs <- list.files()
install.packages(c(print(as.character(pkgs), collapse="\",\"")), repos = NULL)
```

Make matrix from two columns (A, B) of a dataframe and use third column (C) to populate it

```
# For each (A, B), get mean C of the subset dataframe 
xtabs(C ~ B + A, data=aggregate(C ~ B + A, data=df, FUN=mean))
```

Sort a dataframe by two columns

```
# Use - to sort in descending order.
dataframe[ order(-dataframe[,1], dataframe[,2]),]
```