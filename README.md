# StatesExplorerPresentation

This presentation was produced in Slidify and uses two blocks of R code

On the third slide, the R code block is evaluated but not echoed:

```{r ,echo=FALSE}
library(datasets)
library(plyr)
 #Initialize a list of data item names from the data sets for the UI elements to use.
 #Names for the states data set
dsNames <- c("State", "Region", "Population", "Income", "Illiteracy",
                "LifeExpectancy", "MurderRate", "HSGraduationRate",
                "DaysFrost", "Area")
```

This block producses the list of data item nanes in the base dataset used in the application and includes it in the slide using the embedded R syntax: `r dsNames`

On the fourth slide the R code block is echoed but not evaluated:

``` {r, echo=TRUE, eval=FALSE}
if (input$dataSort == 'asc') {
 #For an ascending sort, first sort the data by the selected Y-axis data item
 pdataset <- dataset[order(dataset[match(input$y,names(dataset))]),]
 #Then re-factor the state list that is the X-axis so the plot sorts correctly
 pdataset$State <- factor(pdataset$State, levels = pdataset$State)
} else if (input$dataSort == 'desc') {
 #For an descending sort, first sort the data by the selected Y-axis data item
 pdataset <- dataset[order(-dataset[match(input$y,names(dataset))]),]
 #Then re-factor the state list that is the X-axis so the plot sorts correctly
 pdataset$State <- factor(pdataset$State, levels = pdataset$State)
            } 
```

This block is provided to illustrate the processing necessary to sort the state bar graphs by the data item chosen for the Y-axis.