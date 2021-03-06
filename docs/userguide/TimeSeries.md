# Time Series, Line charts, and Area charts 

As always, we start with loading data.

```Java

```



## Time Series

You can create time series plots easily. The x axis adjusts the scale according to the size of the display area and the number of points displayed. Here's an example:

![](https://jtablesaw.github.io/tablesaw/userguide/images/eda/bush_time_series.png)

```java
Table foxOnly = bush.where(bush.stringColumn("who").equalsIgnoreCase("fox"));

Plot.show(TimeSeriesPlot.create("Fox approval ratings", foxOnly, "date", "approval"));
```

To see more than one series, we add a grouping column to the call to *TimeSeriesPlot.show().*This creates a separate line for each distinct value in that column.  Here the grouping column is "who", which holds the names of the organizations who conducted the poles. 

```Java
Plot.show(
    TimeSeriesPlot.create("George W. Bush approval", bush, "date", "approval", "who"));
```

![](https://jtablesaw.github.io/tablesaw/userguide/images/eda/bush_time_series2.png)

## Line Charts



```Java
Table robberies = Table.read().csv("../data/boston-robberies.csv");
Plot.show(
    LinePlot.create("Monthly Boston Robberies: Jan 1966-Oct 1975", 
              robberies, "Record", "Robberies"));
```

![](https://jtablesaw.github.io/tablesaw/userguide/images/eda/robberies_line.png)

## Area Charts



```Java
Table robberies = Table.read().csv("../data/boston-robberies.csv");
Plot.show(
    LinePlot.create("Monthly Boston Robberies: Jan 1966-Oct 1975", 
              robberies, "Record", "Robberies"));
```

![](https://jtablesaw.github.io/tablesaw/userguide/images/eda/robberies_line.png)