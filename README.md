Data Munging
===
At some point, I worked with some tools that [didn't take more than 1000 data points](http://www.catb.org/jargon/html/C/C-Programmers-Disease.html), but I studying the effects of unusually large data sets in these applications. These are some perl scripts I wrote to "trim" the data sets. They all operate on tab or whitespace separated data files, where the first column is the independent variable.

All the tools have fuller documentation inside them in [POD format](http://perldoc.perl.org/perlpod.html). Running them with the '-m' switch will show this formatted like a manpage.

avgdups
---
If duplicate values of the independent value are present, avgdups will average all the numeric data in the other columns, leaving one row for each value. It will concatenate multiple files first.

pickln
---
pickln will select n lines spaced logarithmically along the full range of the independent variable. It first finds n-logarithmically-spaced points, and then outputs the nearest point to each one, which does mean that it will output duplicates.

pickn
---
pickn will select n lines spaced evenly along the full range of the independent variable. Unlike pickln, it just sorts the file and picks out n lines in an "off-center" fashion, leaving an equal number of lines from the beginning as from the end. It can also select randomly.
