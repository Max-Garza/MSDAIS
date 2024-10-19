A DDL command that allows one to alter an existing relational database object. Can be used in conjunction with the DROP function
```SQL
>> -- Add a primary key
>> ALTER TABLE *table*
>> ADD PRIMARY KEY *column*
>> 
>> --Add a foreign key
>> ALTER TABLE *table*
>> ADD FOREIGN KEY *column* REFERENCES *table*
>> 
>> --Add a CHECK constraint
>> ALTER TABLE *table*
>> ADD CHECK(...)
>> 
>> -- Add a new attribute to an entity
>> ALTER TABLE *table*
>> ADD *column* *datatype* *constraint*
>> 
>> -- Change an attribute's datatype
>> ALTER TABLE *table*
>> ALTER *column* *datatype*
>> 
>> -- Drop a column in an entity
>> ALTER TABLE *table*
>> DROP COLUMN *column*
```

- Background
	- [[Data Definition Language]]
	- [[Relational Database]]
	- [[List of Database Objects]]
	- [[DROP (SQL)]]