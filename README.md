# Practice of Docker

Following a Youtube video:
https://www.youtube.com/watch?v=YFl2mCHdv24

Here is the link to the HUB where you can find containers: 
https://hub.docker.com/

- Location of the PHP intructions code on Docker: https://hub.docker.com/_/php/


***TERMINAL***
    Edxael: ls
Dockerfile  README.md  src/

    Edxael: pwd
/home/edxael/02-Ind-GitHub/100-DockerToDel

    Edxael: sudo docker build -t hello-er .
[sudo] password for edxael: 
Sending build context to Docker daemon  4.608kB
Step 1/3 : FROM php:7.0-apache
7.0-apache: Pulling from library/php
f2aa67a397c4: Pull complete 
4c3122805fd6: Pull complete 
98ce407ee18a: Pull complete 
8a56b8f1ca72: Pull complete 
3eb04e3939f2: Pull complete 
f5ecc66c0a5f: Pull complete 
30ebdb4a78e1: Pull complete 
9e9c0e2ba7f1: Pull complete 
da976026223e: Pull complete 
aa0c3f7bc97b: Pull complete 
34f171b1481c: Pull complete 
1f9e648954f9: Pull complete 
38805c081325: Pull complete 
c8dae101fa30: Pull complete 
Digest: sha256:55871ab88282e37e43d71329d503476f897a50cc315979654bbf91a06046d117
Status: Downloaded newer image for php:7.0-apache
 ---> e18e9bf71cab
Step 2/3 : COPY src/ /var/www/html/
 ---> 237aa2ac6061
Step 3/3 : EXPOSE 80
 ---> Running in 3fb3c7cb2edd
Removing intermediate container 3fb3c7cb2edd
 ---> 988be5b4169a
Successfully built 988be5b4169a
Successfully tagged hello-er:latest

    Edxael: 


   // Now is time to run it: 
    Edxael: sudo docker run -p 80:80 hello-er



Now in the browser address bar: http://localhost/
and you should get: Hello Edxael ZPX


----------
To dont have to re-build the container every time there is a change on the code
    $ sudo docker run -p 80:80 -v /home/edxael/02-Ind-GitHub/100-DockerToDel/src/:/var/www/html/ hello-er