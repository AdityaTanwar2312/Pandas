# Pandas
Learning pandas: Loading data, cleaning data and performing basic functions. You can find different functions and sttributes used in pandas in the intro.ipynb file attached with the respective output they will give if performed on the given data.

Dataset is taken form stack overflow
link for the used data set: https://survey.stackoverflow.co/2019

# To Read and Write data from different types of files

1. CSV format - To read data from a CSV file use method pd.read_csv('< loction of file >')
                To write data to CSV file use method < dataframe name >.to_csv('< Name the file >')
                Note: For a file for tab 'seperated values' change the extention to .tsv and add attribute  sep = '\t'
                (also for reading file)

2. Excel file - Install package using 'pip install xlwt openpyxl xlrd' (To read and write in Excel file)
                To read data from a Excel file use method pd.read_excel('< loction of file >')
                To write data to Excel file use method < dataframe name >.to_excel('< Name the file >')

3. JSON file -  To read data from a JSON file use method pd.read_json('< loction of file >')
                To write data to CSV file use method < dataframe name >.to_json('< Name the file >')
                Note: Include attribute orient = 'records', lines = True for proper format while writing to json files
                while reading from json files change the attributes as per the required values
