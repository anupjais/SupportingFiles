## Create a file in a main directory
```
Dockerfile
```

## Paste the below lines
``` 
FROM node:24-alpine

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

EXPOSE 5173

CMD [“npm”, “run”, “dev”]
```

## Modify/Update vite.config.js with
```
export default defineConfig({
    server: {
        host: "0.0.0.0",
        port: 5173,
    },
    plugins: [react()],
});
```

## To Build the image/container
```
docker build -t vite-test . 
```
## If you're trying for the new build than go with version wise
- e.g
```
docker build -t vite-test:2 .
```

* vite-test is a reference name like variable

## To execute the docker image/container
```
docker run -p 5173:5173 vite-test
```
- '-p' port
- '5173:5173' binding the docker port with webapp


Docker run <image>
Docker run -d <image>; d: detach mode

Docker run –name my-container <image>
Docker run -p 8080:80 <image>; p: port

Docker run -v $(pwd):/app <image>; v: volume
Docker run -it <image> sh; it: interactive

Docker run -it <image> /bin/bash




```
docker ps
```
- ps: process status
```
docker ps -a
```
- ps -a: all processes status

```
docker ps -q
```

```
docker logs <container>
```

```
docker attach <container>
```

```
docker stop <container>
```

```
docker kill <container>
```

```
docker stop $(docker ps -q)
```

```
docker start <container>
```

```
docker start <container>
```

```
docker restart <container>
```

```
docker rm <container>
```
- ; rm: remove

```
docker rm -f <container>
```
- rm -f: remove forcefully

```
docker<container> prune
```
- delete the container entirely of stop container/s

```
docker cp <container>:/path/to/file ./;
```
