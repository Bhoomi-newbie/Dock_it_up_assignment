# Assignment-2
For this task, we had to work with 2 containers and show their connectivity.
### Approach and commands used
<br>
1. Create custom docker network named  `webnet`  using

```
docker network create webnet
```

<br>
2. Write Dockerfile and create an 'index.html' file for building image of web container. <br>
3. Build the image named `mysite` using

 ```
 docker build -t mysite .
 ```

 <br>
4. Run a container named  `web`  on custom docker network accessible on port 6060 of the host using 

```
docker run -d --name web --network webnet -p 6060:80 mysite
```

<br>
5. Create API container using prebuilt image  `hashicorp/http-echo`  on docker network using

```
docker run -d --name api --network webnet hashicorp/http-echo -text="Hello from API"
```

<br>
6. Update Nginx static page to include a link that fetches /api from the API container.<br>
7. Demonstrate connectivity using curl inside the web container using 

```
docker exec -it web curl http://api:5678
```

<br>
 **Curl output** 

```
Hello from API
```
