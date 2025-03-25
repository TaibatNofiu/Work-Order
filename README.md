# Work-Order
 The project will guide you through importing data, applying necessary transformations, adding calculated columns, and creating measures using DAX functions. Follow the steps below to complete the exercise.

 

https://imgur.com/euDVUHy


Instructions

Import Data

 
# Apply Necessary Transformations : 
Check the imported data for any inconsistencies or missing values.
Apply any necessary transformations to clean and prepare the data for analysis. This might include removing duplicates, filling missing values, or changing data types.

 
Add Calculated Columns :  

 
Use the following DAX formula to create a column titled isInBacklog :
                                 isInBacklog = IF([target finish date] < [date extract date], 1, 0)

  Use the following DAX formula to create a column titled Days in Backlog : 
                                Days in Backlog = DATEDIFF([target finish date], [date extract date], DAY)

Use the following DAX formula to create a column titled days in backlog grouping : 
                              days in backlog grouping = SWITCH( TRUE(), [Days in Backlog] > 100, "a - greater than 100", [Days in Backlog] > 50,"b - 50 to 100", [Days in Backlog] >= 11, "c - 11 to 49", [Days in Backlog] > 0, "d - up to 10", [Days in Backlog] <= 0, "not in backlog", "Others")

Use the following DAX formula to create a measure titled Planned Hours: 
Planned Hours = SUM([work order remaining hours])
Use the following DAX formula to create a measure titled Backlog Count:
Backlog Count = COUNTROWS(FILTER(workOrders, [isInBacklog] = 1))
Use the following DAX formula to create a measure titled Backlog Hours : 
Backlog Hours = SUMX(FILTER(workOrders, [isInBacklog] = 1), [Planned Hours])
Use the imported data and calculated columns to create a comprehensive dashboard.
Include visualizations such as charts, tables, and graphs to represent the data.
Ensure that the final dashboard includes the measures Planned Hours, Backlog Count, and Backlog Hours.
Customize the dashboard to match the provided picture.
