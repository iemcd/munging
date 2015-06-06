Data Munging
===
At some point, I worked with some tools that didn't take more than 1000 data points, but I was using large data sets concatenated from different sources. These are some perl scripts I wrote to trim the data sets. They all operate on tab or whitespace separated data files, where the first column is the independent variable.

avgdups
---
If duplicate values of the independent value are present, avgdups will average all the numeric data in the other columns, leaving one row for each value. It will concatenate multiple files first.

pickln
---
pickln will select n lines spaced logarithmically along the full range of the independent variable. It first finds n-logarithmically-spaced points, and then outputs the nearest point to each one, which does mean that it will output duplicates.

pickn
---
pickn will select n lines spaced evenly along the full range of the independent variable. Unlike pickln, it just sorts the file and picks out n lines in an "off-center" fashion, leaving an equal number of lines from the beginning as from the end. It can also select randomly.
