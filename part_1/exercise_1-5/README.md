# Exercise 1.5

## Terminal 1

```
Script started on 2019-12-03 10:14:59+0000
[root@ip-172-31-20-228 part_1]# docker run -it --name exercise1_4 ubuntu sh -c 'echo "Input website:"; read website; echo "Searching.."; sleep 1; curl http://$websit 
e;'
Unable to find image 'ubuntu:latest' locally
latest: Pulling from library/ubuntu
45d437916d57: Pull complete 
Digest: sha256:6e9f67fa63b0323e9a1e587fd71c561ba48a034504fb804fd26fd8800039835d
Status: Downloaded newer image for ubuntu:latest
Input website:
helsinki.fi
Searching..
<!DOCTYPE HTML PUBLIC "-//IETF//DTD HTML 2.0//EN">
<html><head>
<title>301 Moved Permanently</title>
</head><body>
<h1>Moved Permanently</h1>
<p>The document has moved <a href="http://www.helsinki.fi/">here</a>.</p>
</body></html>
[root@ip-172-31-20-228 part_1]# exit
exit

Script done on 2019-12-03 10:17:55+0000

```

## Terminal 2

```
Script started on 2019-12-03 10:16:20+0000
[root@ip-172-31-20-228 part_1]# docker ps
CONTAINER ID        IMAGE               COMMAND                   CREATED             STATUS              PORTS               NAMES
92ec1612f31d        ubuntu              "sh -c 'echo \"Input …"   38 seconds ago      Up 37 seconds                           exercise1_4
[root@ip-172-31-20-228 part_1]# docker exec -it exercise1_4 bash
root@92ec1612f31d: /root@92ec1612f31d:/# apt-get -qq update
root@92ec1612f31d: /root@92ec1612f31d:/# apt-get install curl
Reading state information... Done
The following additional packages will be installed:
  ca-certificates krb5-locales libasn1-8-heimdal libcurl4 libgssapi-krb5-2 libgssapi3-heimdal libhcrypto4-heimdal libheimbase1-heimdal libheimntlm0-heimdal
  libhx509-5-heimdal libk5crypto3 libkeyutils1 libkrb5-26-heimdal libkrb5-3 libkrb5support0 libldap-2.4-2 libldap-common libnghttp2-14 libpsl5 libroken18-heimdal
  librtmp1 libsasl2-2 libsasl2-modules libsasl2-modules-db libsqlite3-0 libssl1.1 libwind0-heimdal openssl publicsuffix
Suggested packages:
  krb5-doc krb5-user libsasl2-modules-gssapi-mit | libsasl2-modules-gssapi-heimdal libsasl2-modules-ldap libsasl2-modules-otp libsasl2-modules-sql
The following NEW packages will be installed:
  ca-certificates curl krb5-locales libasn1-8-heimdal libcurl4 libgssapi-krb5-2 libgssapi3-heimdal libhcrypto4-heimdal libheimbase1-heimdal libheimntlm0-heimdal
  libhx509-5-heimdal libk5crypto3 libkeyutils1 libkrb5-26-heimdal libkrb5-3 libkrb5support0 libldap-2.4-2 libldap-common libnghttp2-14 libpsl5 libroken18-heimdal
  librtmp1 libsasl2-2 libsasl2-modules libsasl2-modules-db libsqlite3-0 libssl1.1 libwind0-heimdal openssl publicsuffix
0 upgraded, 30 newly installed, 0 to remove and 2 not upgraded.
Need to get 4834 kB of archives.
After this operation, 14.8 MB of additional disk space will be used.
Do you want to continue? [Y/n] y
0% [Working]
Get:1 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 libssl1.1 amd64 1.1.1-1ubuntu2.1~18.04.5 [1300 kB]                                  
100% [Working]       
Fetched 4834 kB in 0s (9691 kB/s)
debconf: delaying package configuration, since apt-utils is not installed
Selecting previously unselected package libssl1.1:amd64.
(Reading database ... 
(Reading database ... 5%
(Reading database ... 100%
(Reading database ... 4046 files and directories currently installed.)
Preparing to unpack .../00-libssl1.1_1.1.1-1ubuntu2.1~18.04.5_amd64.deb
Setting 
```