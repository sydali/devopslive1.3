# Devopslive10 -Assignment 1
## Part 3

 



```


root@dice-devops:/home# docker volume create my_volume
my_volume


root@dice-devops:/home# docker volume inspect my_volume
[
    {
        "CreatedAt": "2023-11-10T05:49:54Z",
        "Driver": "local",
        "Labels": null,
        "Mountpoint": "/var/lib/docker/volumes/my_volume/_data",
        "Name": "my_volume",
        "Options": null,
        "Scope": "local"
    }
]



root@dice-devops:/home# docker run --name NGIN  -v my_volume:/usr/share/nginx/html  -p 8080:80   -d nginx
41552915e7d6621d09ea022be90d0a711f53adca4f4ee04c0ffe2541cb4ae9b0
root@dice-devops:/home# docker ps
CONTAINER ID   IMAGE        COMMAND                  CREATED         STATUS             PORTS                                       NAMES
41552915e7d6   nginx        "/docker-entrypoint.…"   3 seconds ago   Up 2 seconds       0.0.0.0:8080->80/tcp, :::8080->80/tcp       NGIN
1c421046eb02   unicorn:v1   "python3 main.py"        5 hours ago     Up About an hour   0.0.0.0:8000->8000/tcp, :::8000->8000/tcp   latest_unicorns
8b121467c308   nginx        "/docker-entrypoint.…"   18 hours ago    Up 18 hours                                                    pedantic_nash
3ea6aa7e4382   nginx        "/docker-entrypoint.…"   44 hours ago    Up 44 hours        80/tcp                                      blissful_shtern


 
```

![image](https://github.com/sydali/devopslive1.3/assets/449393/2d70f043-a530-4786-bfbe-4b8157a5a96b)

```
root@dice-devops:/home# docker cp index.html NGIN:/usr/share/nginx/html
Successfully copied 2.05kB to NGIN:/usr/share/nginx/html
root@dice-devops:/home# docker stop NGIN
NGIN
root@dice-devops:/home# docker ps
CONTAINER ID   IMAGE        COMMAND                  CREATED        STATUS             PORTS                                       NAMES
1c421046eb02   unicorn:v1   "python3 main.py"        5 hours ago    Up About an hour   0.0.0.0:8000->8000/tcp, :::8000->8000/tcp   latest_unicorns
8b121467c308   nginx        "/docker-entrypoint.…"   18 hours ago   Up 18 hours                                                    pedantic_nash
3ea6aa7e4382   nginx        "/docker-entrypoint.…"   44 hours ago   Up 44 hours        80/tcp                                      blissful_shtern
root@dice-devops:/home# docker start NGIN
NGIN
root@dice-devops:/home# docker ps
CONTAINER ID   IMAGE        COMMAND                  CREATED          STATUS             PORTS                                       NAMES
41552915e7d6   nginx        "/docker-entrypoint.…"   15 minutes ago   Up 1 second        0.0.0.0:8080->80/tcp, :::8080->80/tcp       NGIN
1c421046eb02   unicorn:v1   "python3 main.py"        5 hours ago      Up About an hour   0.0.0.0:8000->8000/tcp, :::8000->8000/tcp   latest_unicorns
8b121467c308   nginx        "/docker-entrypoint.…"   18 hours ago     Up 18 hours                                                    pedantic_nash
3ea6aa7e4382   nginx        "/docker-entrypoint.…"   44 hours ago     Up 44 hours        80/tcp                                      blissful_shtern


```

 ![image](https://github.com/sydali/devopslive1.3/assets/449393/98b78248-b1d8-4557-9430-4538e1ac028e)





```

root@dice-devops:/home# docker pull httpd
Using default tag: latest
latest: Pulling from library/httpd
578acb154839: Already exists
c1a8c8567b78: Pull complete
10b9ab03bf45: Pull complete
74dbedf7ddc0: Pull complete
6a3b76b70f73: Pull complete
Digest: sha256:4e24356b4b0aa7a961e7dfb9e1e5025ca3874c532fa5d999f13f8fc33c09d1b7
Status: Downloaded newer image for httpd:latest
docker.io/library/httpd:latest
root@dice-devops:/home# docker images
REPOSITORY              TAG       IMAGE ID       CREATED        SIZE
unicorn                 v1        94d5dc12ddea   17 hours ago   1.04GB
rollymaan/assignmet-1   v1        94d5dc12ddea   17 hours ago   1.04GB
redis                   latest    7f27d60cb8e0   8 days ago     138MB
nginx                   latest    c20060033e06   9 days ago     187MB
httpd                   latest    7f6a969e81a5   9 days ago     168MB
alpine                  latest    8ca4688f4f35   6 weeks ago    7.34MB
centos                  latest    5d0da3dc9764   2 years ago    231MB
root@dice-devops:/home# docker run --name HTTPD   -v my_volume:/usr/local/apache2/htdocs   -p 8081:80   -d httpd
e11ecac27c7a45206c3f86d20abcb81573384d3c8060f23b5744b5f096f9b27c

root@dice-devops:/home# docker ps
CONTAINER ID   IMAGE        COMMAND                  CREATED          STATUS          PORTS                                       NAMES
e11ecac27c7a   httpd        "httpd-foreground"       22 seconds ago   Up 21 seconds   0.0.0.0:8081->80/tcp, :::8081->80/tcp       HTTPD
1c421046eb02   unicorn:v1   "python3 main.py"        5 hours ago      Up 2 hours      0.0.0.0:8000->8000/tcp, :::8000->8000/tcp   latest_unicorns
8b121467c308   nginx        "/docker-entrypoint.…"   18 hours ago     Up 18 hours                                                 pedantic_nash
3ea6aa7e4382   nginx        "/docker-entrypoint.…"   44 hours ago     Up 44 hours     80/tcp                                      blissful_shtern


```

![image](https://github.com/sydali/devopslive1.3/assets/449393/5e7f6f12-6c04-469e-98b2-bbac04ff0a23)




 

 
