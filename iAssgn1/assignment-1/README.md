<h1>Assignment 1</h1>
For this assignment, we had to create our custom website and run it using docker
<h3> Approach and commands used</h3>
1. Create a Dockerfile(for serving page through nginx) and an "index.html".
<br><br>
2. Build an image named "bhumi-site" using

```
docker build -t  bhumi-site .
```

<br>
3. Run the container named "asgn_one" so it’s accessible on port 7070 on the host using

```
docker run -d --name asgn_one -p 7070:80 bhumi-site
```
<br>
4. Test using curl

```
curl http://localhost:7070
```

<br>
<h5>curl output</h5> 

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bhoomi Garg</title>
    <style>
        body { font-family: Arial, sans-serif; background-color: #f0f8ff; text-align: center; margin-top: 50px; }
        h1 { color: #0077cc; }
        p { color: #333; }
    </style>
</head>
<body>
    <h1>Welcome to My Site!</h1>
    <p>Hello! I am Bhoomi Garg. I am a 1st Year Btech student at NITK.</p>
    <p>I am excited to take part in Dock It Up and learn about Docker and devops.</p>
</body>
</html>
```

<br>

<br>
5. Stop and remove the container after testing using

```
docker stop asn_one
docker rm asn_one
```

