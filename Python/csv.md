### CSV module

#### CSV files

- CSV = Comma Separated Values
- for importing / exporting spreadsheets and databases
- to store a large number of variables, simplified spreadsheets where the content is stored in plaintext
- normally comma separated values in rows
- CSV module helps to read and write csv files, has a dialect for handling Microsoft Excel files

### Methods

- ```csv.reader```
- ```csv.writer```
- ```csv.DictReader```
- ```csv.DictWriter```
- ```csv.OrderedDict```
- ```csv.get_dialect```
- ```csv.list_dialects```

#### Reading CSV files

- to read data froma csv file, you have to use the reader function to generate a reader object.
- reader function takes every row, and makes a list of all columns

```
import csv
with open('my.csv', 'rt') as f:
  reader = csv.reader(f)
  for row in reader:
    print(row)
```
OR

```
import csv
import sys

f = open(sys.argv[1], 'rt')
reader = csv.reader(f)
for row in reader:
  print(row)

f.close()
```

### Working with CSV files simple example

```
car myCSV.csv
```

```
firstName,lastName, age
" Mary Ann",Smith, 18
John, Doe, 26
Kate,Wilson, 30
```

```
import csv

f = open('myCSV.csv','rt')
reader = csv.reader(f)

row_num = 0
for row in reader:
  #save header row
  if row_num == 0:
    header = row
  else:
    col_num = 0
    for col in row:
      print('%-8s: %s'%(header[col_num],col))
      col_num += 1
    row_num += 1

f.close()
```
#### Writing to CSV files

- the ```csv.writer``` method  crates an object suitable for writing data.
- ```csv.writerow``` help you to itereate oer the data row by row

```
import csv

infile = open('test.csv', 'rb')
reader = csv.reader(infile)
out = open('test_transformed.csv','wb')
writer = csv.writer(out, delimiter='',quotechar='"',quoting = csv.QUOTE_ALL)

for row in reader:
  write.writerow(row)

infile.close()
out.close()
```

Quoting options:
- ```csv.QUOTE_ALL```: quote everything
- ```csv.QUOTE_MINIMAL```: quote fields with special chars
- ```csv.QUOTE_NONNUMERIC```: quote non integers and non floats
- ```csv.QUOTE_NONE``` : quote nothing

Reference:
-[](http://www.pythonforbeginners.com/systems-programming/using-the-csv-module-in-python/)
