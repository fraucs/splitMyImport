Parallel Database Import Script
============

This shell script is designed to import databases from a provided MySQL dump file in parallel, with a limit on the maximum number of concurrent jobs.

WARNING: The databases to be imported must be present on the local engine!

Usage
============
Prerequisites
-----------
Ensure you have MySQL installed and accessible from the command line.
The databases to be imported must exist on the local MySQL server.

Script Execution
----------
To run the script, provide the path to your MySQL dump file as the first argument.
~~~shell
./splitMyImport.sh <dump_file>
~~~
### Example ###
~~~shell
./script.sh my_database_dump.sql
~~~
Configuration
=======
The script comes with a few configurable settings:

Maximum Number of Parallel Jobs
---------
By default, the script is set to run a maximum of 4 parallel jobs. You can adjust this as needed.
~~~shell
max_jobs=4
~~~
Exclude Databases
-------
The script excludes certain databases from the import process by default.
~~~shell
exclude_dbs="sys|information_schema|performance_schema|database"
~~~
You can modify this list according to your requirements.
Just add a "|"  with the DB you want to exclude
### Example ###
~~~shell
exclude_dbs="sys|information_schema|performance_schema|database|**noMe**"
~~~
### Or Multiple ###
~~~shell
exclude_dbs="sys|information_schema|performance_schema|database|**noMe**|**AlsoNoMe**"
~~~