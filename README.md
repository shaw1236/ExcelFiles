- Prerequisite modules

pandas@0.25.3

openpyxl3.0.1 

xlrd@1.2.0

- Install xlsfile

pip install xlsfile-shaw1236

- How to use xlsfile?

from xlsfile.xlsFile import xlsFile 

print("Test csv file")

contents = xlsFile.readcsv("test2.csv")

xlsFile.writecsv("test3.csv", contents)

input = {}

input["name"] = ["Test1", "Test2", "Test3"]

input["email"] = ["test1@gmail.com", "test2@yahoo.com", "test3@gmail.com"]

input["name"].append("Test4") 

input["email"].append("test@yahoo.com") 

filename = "testfamily.xlsx"

print("\nExcel file test")

xlsFile.write(filename, input)

contents = xlsFile.read(filename)

print(contents)

print("\nExcel to csv")

xlsFile.xls2csv(filename, filename.replace(".xlsx", ".csv"))

print("\ncsv to Excel")

xlsFile.csv2xls(filename.replace(".xlsx", ".csv"), "testfamily2.xlsx")

contents = xlsFile.read("testfamily2.xlsx")

print(contents)
