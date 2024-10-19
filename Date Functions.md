SQL functions pertaining to date data
```SQL
>> GETDATE() -- Get current date
>> DAY(input) -- Extract day
>> MONTH(input) -- Extract month
>> YEAR(input) -- Extract year
>> DATENAME(datepart, input) -- Get name associated with datepart
>> DATEPART(datepart, input) -- Get datepart
>> DATEADD(interval, number, input) -- Add an interval to a given date
>> DATEFROMPARTS(yearinput, monthinput, dayinput) -- Create a date from parts
>> ISDATE(input) -- Check if something is a date
>> DATE_BUCKET(datepart, number, input) -- Create date groups
```

- Background
	- [[Date SQL Datatype]]
	- [[SQL]]