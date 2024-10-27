```Python
>> # Load data
>> df = pd.read_csv("data.csv")
>> 
>> # Sort values
>> df.sort_values(by=['col1'], ascending=True)
>> 
>> # Plotting data
>> df.plot(x=OBJECT, y=OBJECT, kind='line')
>> df.plot.bar(stacked=False)
>> df.plot.area(alpha=X)
>> df['X'].plot.kde()
>> df['X'].plot.hist(bins=10)
>> df.plot.scatter(x=OBJECT, y=OBJECT)
>> df.plot.box()
>> df.plot.(kind='pie', y=OBJECT, autopct='%1.0f%%')
>> 
>> # Exploring data
>> df.info()
>> df.describe()
>> df.head()
>> df.sample()
>> df.tail()
>> 
>> # Filtering data
>> df['col']
>> df[df['col'] > 10]
>> df[['col1','col2']]
>> df[:,:]
>> 
>> # Column Operations
>> df.loc[df['col'] > 10, 'col2'] = 1
>> df['col'].fillna()
>> df['col'].sum()
>> df['col'].mean()
>> df['col'].stdev()
>> df['col'].sem()
>> df['col'].min()
>> df['col'].max()
>> 
>> # Joins and append
>> pd.concat([df1, df2]).reset_index(drop=True) # APPEND
>> pd.merge(df1, df2, left_on='id', right_on='id', how='left') # LEFT RIGHT INNER OUTER
>> 
>> # Group by
>> df.groupby('col1')['col2'].sum()
>> 
>> # Cross-tab
>> pd.crosstab(df['col1'], df['col2'], dropna=False) # CONTINGENCY TABLE
```

- Background
	- [[Pandas]]
	- [[Types of Joins]]
	- [[Statistical Summary]]