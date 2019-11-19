-- Prerequisite modules
-pandas@0.25.3
-openpyxl3.0.1 
-xlrd@1.2.0

-- Install xlsfile
pip install xlsfile --user

-- How to use xlsfile?

from xlsfile import xlsfile 

## Csv file testing
print("Test csv file")
contents = xlsfile.readcsv("test2.csv")
xlsfile.writecsv("test3.csv", contents)

input = {}
input["name"] = ["Test1", "Test2", "Test3"]
input["email"] = ["test1@gmail.com", "test2@yahoo.com", "test3@gmail.com"]
input["name"].append("Test4") 
input["email"].append("test@yahoo.com") 

filename = "testfamily.xlsx"

## Excel file test
print("\nExcel file test")
xlsfile.write(filename, input)
contents = xlsfile.read(filename)
print(contents)

## Excel to csv
print("\nExcel to csv")
xlsfile.xls2csv(filename, filename.replace(".xlsx", ".csv"))

## csv to Excel
print("\ncsv to Excel")
xlsfile.csv2xls(filename.replace(".xlsx", ".csv"), "testfamily2.xlsx")
contents = xlsfile.read("testfamily2.xlsx")
print(contents)