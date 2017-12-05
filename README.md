

import pandas as pd
csvdata = pd.read_csv('C:\\Users\\Sandipan Sen\\Desktop\\Online_Retail.csv')
print(csvdata)

csvdata.shape

print(csvdata.head(10))

print(csvdata.describe())

#Filter a column (using drop)
df2 = csvdata.drop(['InvoiceDate', 'CustomerID','Country'], axis = 1)
print(df2)

#Filter a column (selecting the required column)

df2=csvdata['UnitPrice']
print(df2)

#sort data by price
df3=csvdata.sort_values(['UnitPrice'])
print(df3)

#group data by invoice number 

df4=csvdata.groupby('InvoiceNo').sum()
print(df4)

#histogram
csvdata.hist()

# Categorical variable Analysis
csvdata.Description.value_counts(ascending=True)
csvdata.InvoiceNo.value_counts(ascending=True)
csvdata.StockCode.value_counts(ascending=True)

#boxplot
csvdata.boxplot(column=['Quantity', 'UnitPrice'])
