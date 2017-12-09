# Simple-Spreadsheet-Analysis

Divide the "Date of Contact" column into month, day and year columns by using 'text to columns' function in excel
Save excel as csv file

Continue with R

data=read.csv(file.choose())      # read csv file 
freqtable=as.data.frame(table(date$month))       # create frequency table
newdata=transform(freqtable, percentage=100*(prop.table(Freq)))   # calculate percentage
sum(newdata$percentage)   # cross check


> newdata
   Var1 Freq percentage
1     1  961   8.384958
2     2  875   7.634587
3     3  961   8.384958
4     4  930   8.114475
5     5  961   8.384958
6     6  930   8.114475
7     7  961   8.384958
8     8  978   8.533287
9     9  960   8.376232
10   10  992   8.655440  ############
11   11  960   8.376232
12   12  992   8.655440  ############

> sum(newdata$percentage)
[1] 100

October (10) and December (12) are the months that the team contact the greatest percentage of its clients.
