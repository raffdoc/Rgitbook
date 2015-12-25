
## Summarising Data
### Tables


```r
> testDataDir <- system.file("Database", package="ChainLadder")
> fn.csv <- paste(testDataDir,"/TestData.csv", sep="")
> myData <- read.csv(fn.csv, stringsAsFactors=TRUE)
```

```
Warning in file(file, "rt"): cannot open file '/TestData.csv': No such file
or directory
```

```
Error in file(file, "rt"): cannot open the connection
```

```r
> head(myData)
```

```
Error in head(myData): object 'myData' not found
```

```r
> require(data.table)
```

```
Loading required package: data.table
data.table 1.9.6  For help type ?data.table or https://github.com/Rdatatable/data.table/wiki
The fastest way to learn (by data.table authors): https://www.datacamp.com/courses/data-analysis-the-data-table-way
```

```r
> myData <- data.table(myData)
```

```
Error in data.table(myData): object 'myData' not found
```

### Visual


```r
> myData[order(dev), cvalue:=cumsum(value), by=list(origin, lob)]
```

```
Error in eval(expr, envir, enclos): object 'myData' not found
```

```r
> xyplot(value/1e3 ~ dev | lob, groups=origin, 
+                    data=myData, main="Incremental developments",
+                    scales="free", t="l", as.table=TRUE, layout=c(3,4))
```

```
Error in eval(substitute(groups), data, environment(x)): object 'myData' not found
```

```r
> xyplot(cvalue/1e3 ~ dev | lob, groups=origin, 
+                   data=myData, main="Cumulative developments",
+         scales="free", t="l", as.table=TRUE, layout=c(3,4))
```

```
Error in eval(substitute(groups), data, environment(x)): object 'myData' not found
```

```r
> #print(IncrPlot, position=c(0, 0, 0.5, 1), more=TRUE)
> #print(CumPlot, position=c(0.5, 0, 1, 1))
```

Note that the `echo = FALSE` parameter was added to the code chunk to prevent printing of the R code that generated the plot.

```r
> latestData <- myData[, .SD[max(dev)] , by=list(origin, lob) ]
```

```
Error in eval(expr, envir, enclos): object 'myData' not found
```

```r
> head(latestData)
```

```
Error in head(latestData): object 'latestData' not found
```
