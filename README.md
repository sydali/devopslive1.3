# Devopslive10 -Assignment 1
## Part 3

Step1: Pick Docker  
   

Step 2: Run Docker

```
root@dice-devops:/home# docker run -p 8000:8000  -d -t --name latest_unicorn    unicorn:v1
1c421046eb02bccfb4a8363299892c1d27bd9b5f9b8c8e0d5705f79a1509913c
root@dice-devops:/home# docker ps
CONTAINER ID   IMAGE        COMMAND                  CREATED         STATUS        PORTS                                       NAMES
1c421046eb02   unicorn:v1   "python3 main.py"        2 seconds ago   Up 1 second   0.0.0.0:8000->8000/tcp, :::8000->8000/tcp   latest_unicorn
8b121467c308   nginx        "/docker-entrypoint.…"   13 hours ago    Up 13 hours                                               pedantic_nash
3ea6aa7e4382   nginx        "/docker-entrypoint.…"   39 hours ago    Up 39 hours   80/tcp                                      blissful_shtern

```

![image](https://github.com/sydali/devopslive1.2/assets/449393/53b1fe0f-db9f-486c-84a4-d57fa4b53b2f)





Step 3: Docker Commands

