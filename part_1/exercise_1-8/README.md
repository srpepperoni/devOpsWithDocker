# Exercise 1.8

```
Script started on 2019-12-07 17:27:03+0000
[root@ip-172-31-20-228 part_1]# docker run devopsdockeruh/first_volume_exercise
(node:1) ExperimentalWarning: The fs.promises API is experimental
Wrote to file /usr/app/logs.txt
Closing file
[root@ip-172-31-20-228 part_1]# docker ps -a
CONTAINER ID        IMAGE                                  COMMAND             CREATED             STATUS                     PORTS               NAMES
88f78119631b        devopsdockeruh/first_volume_exercise   "node index"        11 seconds ago      Exited (0) 7 seconds ago                       adoring_wilson
[root@ip-172-31-20-228 part_1]# docker cp "/usr/app" .
[root@ip-172-31-20-228 part_1]# docker run -v $(pwd)/app:/usr/app devopsdockeruh/first_volume_exercise
(node:1) ExperimentalWarning: The fs.promises API is experimental
Wrote to file /usr/app/logs.txt
Wrote to file /usr/app/logs.txt
Wrote to file /usr/app/logs.txt
Wrote to file /usr/app/logs.txt
Wrote to file /usr/app/logs.txt
Wrote to file /usr/app/logs.txt
Closing file
[root@ip-172-31-20-228 part_1]# cd app
[root@ip-172-31-20-228 app]# cat logs.txt 
Sat, 07 Dec 2019 17:28:32 GMT
Sat, 07 Dec 2019 17:28:35 GMT
Sat, 07 Dec 2019 17:28:38 GMT
Sat, 07 Dec 2019 17:28:41 GMT
Secret message is:
"Volume bind mount is easy"
Sat, 07 Dec 2019 17:28:47 GMT
[root@ip-172-31-20-228 app]# exit
exit

Script done on 2019-12-07 17:29:01+0000

```

