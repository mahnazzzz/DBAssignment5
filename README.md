# Assignment 5

You can find assignments discription [her](https://github.com/datsoftlyngby/soft2019spring-databases/blob/master/assignments/assignment5.md)

#### Use the docker for connect to mysql workbench and loading the files into a database.

```sh
$ winpty docker exec -it my_mysql bash
```
#### For download the data and unzip data
```sh
root@e828ce7aa1e9:/# apt-get install update
root@e828ce7aa1e9:/# apt-get update
root@e828ce7aa1e9:/# apt-get install wget
root@e828ce7aa1e9:/# apt-get install p7zip-full
root@e828ce7aa1e9:/# wget https://archive.org/download/stackexchange/coffee.stackexchange.com.7z
root@e828ce7aa1e9:/# 7z e coffee.stackexchange.com.7z
```
#### Connect to mysql 
```sh
root@e828ce7aa1e9:/# mysql -u <username> -p --local-infile stackoverflow
```
#### Load the data into table
```sh
mysql>  set global local_infile = 1;
mysql> load xml local infile '<DATANAME>.xml' into table <TABELNAME> rows identified by '<row>';
```
> Copy sql statement from [here](https://gist.github.com/emanoelbarreiros/c164a60e98a7482cde22) into mysql workbench and run the statment. (You have to delete some of the wrong statement from line 95-125)

