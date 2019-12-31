# Exercise 1.2

```
Script started on 2019-11-13 21:43:46+0000
[root@ip-172-31-20-228 part_1]# docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS                      PORTS               NAMES
559aefaebb59        alpine              "/bin/sh"                11 minutes ago      Exited (0) 11 minutes ago                       quirky_heisenberg
bd2ffa3709b0        hello-world         "/hello"                 12 minutes ago      Exited (0) 12 minutes ago                       practical_shannon
52a559c51bf3        nginx               "nginx -g 'daemon of…"   12 minutes ago      Up 12 minutes               80/tcp              vigorous_bell
[root@ip-172-31-20-228 part_1]# docker stop 52a559c51bf3
52a559c51bf3
[root@ip-172-31-20-228 part_1]# docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS                      PORTS               NAMES
559aefaebb59        alpine              "/bin/sh"                12 minutes ago      Exited (0) 12 minutes ago                       quirky_heisenberg
bd2ffa3709b0        hello-world         "/hello"                 13 minutes ago      Exited (0) 13 minutes ago                       practical_shannon
52a559c51bf3        nginx               "nginx -g 'daemon of…"   13 minutes ago      Exited (0) 8 seconds ago                        vigorous_bell
[root@ip-172-31-20-228 part_1]# docker rm 559aefaebb59 bd2ffa3709b0 52a559c51bf3
559aefaebb59
bd2ffa3709b0
52a559c51bf3
[root@ip-172-31-20-228 part_1]# docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
[root@ip-172-31-20-228 part_1]# docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
nginx               latest              540a289bab6c        3 weeks ago         126MB
alpine              latest              965ea09ff2eb        3 weeks ago         5.55MB
hello-world         latest              fce289e99eb9        10 months ago       1.84kB
[root@ip-172-31-20-228 part_1]# docker rmi 540a289bab6c 965ea09ff2eb fce289e99eb9
Untagged: nginx:latest
Untagged: nginx@sha256:922c815aa4df050d4df476e92daed4231f466acc8ee90e0e774951b0fd7195a4
Deleted: sha256:540a289bab6cb1bf880086a9b803cf0c4cefe38cbb5cdefa199b69614525199f
Deleted: sha256:ab18af7cee69bfb22c1771e54d5e0e68b1a1bf57bb46516142da0380b1771f4a
Deleted: sha256:02f7daf1e14541cd61a3dda1a61cc0f78fee8de2984d488b8ba5bbd3cbad9b57
Deleted: sha256:b67d19e65ef653823ed62a5835399c610a40e8205c16f839c5cc567954fcf594
Untagged: alpine:latest
Untagged: alpine@sha256:c19173c5ada610a5989151111163d28a67368362762534d8a8121ce95cf2bd5a
Deleted: sha256:965ea09ff2ebd2b9eeec88cd822ce156f6674c7e99be082c7efac3c62f3ff652
Deleted: sha256:77cae8ab23bf486355d1b3191259705374f4a11d483b24964d2f729dd8c076a0
Untagged: hello-world:latest
Untagged: hello-world@sha256:c3b4ada4687bbaa170745b3e4dd8ac3f194ca95b2d0518b417fb47e5879d9b5f
Deleted: sha256:fce289e99eb9bca977dae136fbe2a82b6b7d4c372474c9235adc1741675f587e
Deleted: sha256:af0b15c8625bb1938f1d7b17081031f649fd14e6b233688eea3c5483994a66a3
[root@ip-172-31-20-228 part_1]# docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
[root@ip-172-31-20-228 part_1]# exit
exit

Script done on 2019-11-13 21:46:13+0000

```

