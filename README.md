# Simple-Spreadsheet-Analysis

Divide the "Date of Contact" column into month, day and year columns by using 'text to columns' function in excel
Save excel as csv file

Continue with R

monthcolum<-read.table("clipboard",header = T)  # save the month column as monthcolumn
freqtable=as.data.frame(table(monthcolum$month))  # create frequency table
newdata=transform(freqtable, percentage=100*(prop.table(Freq)))  # create percentage table
sum(newdata$percentage)  # cross check


> freqtable=as.data.frame(table(monthcolum$month))

> freqtable
   Var1 Freq
1     1   60
2     2   64
3     3   58
4     4   52
5     5   69
6     6   77
7     7   66
8     8   79
9     9  121
10   10  213
11   11   65
12   12   76

> newdata=transform(freqtable, percentage=100*(prop.table(Freq)))
> newdata
   Var1 Freq percentage
1     1   60        6.0
2     2   64        6.4
3     3   58        5.8
4     4   52        5.2
5     5   69        6.9
6     6   77        7.7
7     7   66        6.6
8     8   79        7.9
9     9  121       12.1
10   10  213       21.3   #The highest percentage
11   11   65        6.5
12   12   76        7.6

> sum(newdata$percentage)
[1] 100

October (10) is the month that the team contact the greatest percentage of its clients
