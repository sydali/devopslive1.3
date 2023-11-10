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



![image](https://github.com/sydali/devopslive1.3/assets/449393/966b1477-1f5e-4625-a7c7-87b9085e0721)

 
```
