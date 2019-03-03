# Assignment 5

You can find assignments discription [her](https://github.com/datsoftlyngby/soft2019spring-databases/blob/master/assignments/assignment5.md)

#### Use the docker for connect to mysql workbench and loading the files into a database.

```sh
$ winpty docker exec -it my_mysql bash
```
#### For download the data and unzip data
```sh
$  root@e828ce7aa1e9:/# apt-get install update
$  root@e828ce7aa1e9:/# apt-get update
$  root@e828ce7aa1e9:/# apt-get install wget
$  root@e828ce7aa1e9:/# apt-get install p7zip-full
$  root@e828ce7aa1e9:/# wget https://archive.org/download/stackexchange/coffee.stackexchange.com.7z
$  root@e828ce7aa1e9:/# 7z e coffee.stackexchange.com.7z
```
#### Connect to mysql 
```sh
root@e828ce7aa1e9:/# mysql -u <username> -p --local-infile stackoverflow
```
#### Load the data into table
```sh
$ mysql>  set global local_infile = 1;
$ mysql> load xml local infile '<DATANAME>.xml' into table <TABELNAME> rows identified by '<row>';
```
> Copy sql statement from [here](https://gist.github.com/emanoelbarreiros/c164a60e98a7482cde22) into mysql workbench and run the statment. (You have to delete some of the wrong statement from line 95-125)

Exercise 1
Write a stored procedure denormalizeComments(postID) that moves all comments for a post (the parameter) into a json array on the post.

Exercise 2
Create a trigger such that new adding new comments to a post triggers an insertion of that comment in the json array from exercise 1.

Exercise 3
Rather than using a trigger, create a stored procedure to add a comment to a post - adding it both to the comment table and the json array

Exercise 4
Make a materialized view that has json objects with questions and its answeres, but no comments. Both the question and each of the answers must have the display name of the user, the text body, and the score.

Exercise 5
Using the materialized view from exercise 4, create a stored procedure with one parameter keyword, which returns all posts where the keyword appears at least once, and where at least two comments mention the keyword as well.
