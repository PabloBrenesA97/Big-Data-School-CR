### sqoop cheat sheet

#### sqoop help
```
sqoop help import
sqoop help export
sqoop help merge
```

#### sqoop list-xx
```
sqoop list-databases
sqoop list-tables
```

#### sqoop import 
```
sqoop import 
--connect 'jdbc:mysql://localhost:3306/retail_db' \
--username
--password
--table 
--columns
--where
--target-dir or --warehouse-dir (if none are mentioned, o/p goes to /user/cloudera/)
--append
--bindir (Output directory for compiled objects i.e. .jar and .class)
--outdir (Output directory for generated code i.e. .java)
--as-sequencefile or --as-avrodatefile or --as-textfile or --as-parquetfile
--compress
--compression-codec
--null-string
--null-non-string

#incremental
--incremental append or --incremental lastmodified
--check-column
--last-value

#delimiters/formatting
--enclosed-by '\"'
--optionally-enclosed-by '\"'
--escaped-by
--fields-terminated-by
--lines-terminated-by
<repeat for --input-.....>

#hive
--hive-import
--hive-database
--hive-table
--create-hive-table
--hive-overwrite
--hive-partition-key
--hive-partition-value
```
##### sqoop import-all-tables
```
sqoop import-all-tables
--connect 'jdbc:mysql://localhost:3306/retail_db' \
--username
--password
--warehouse-dir
--as-sequencefile or --as-avro-datefile or --as-textfile
--compress
--compression-codec

#delimiters/formatting
--enclosed-by '\"'
--optionally-enclosed-by '\"'
--escaped-by
--fields-terminated-by
--lines-terminated-by
<repeat for --input-.....>

#hive
<same as above>
```
##### sqoop export
###### Very important: For export to work correctly, the table must have a primatry key
```
sqoop export
--connect 'jdbc:mysql://localhost:3306/retail_db' \
--username
--password
--export-dir
--table
--update-key <col1>
--update-mode updateonly or --update-mode allowinsert
```
#### sqoop job
```
sqoop job --create job1 -- import....
sqoop job --list
sqoop job --exec job1
```
#### sqoop merge
```
sqoop merge
--class-name
--jar-name
--merge-key
--new-data
--onto
--target-dir
```
#### sqoop eval
```
sqoop eval
--query
```
