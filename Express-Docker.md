## To initialize the express project
- Step-1
```
npm init -y
```

- Step-2: create a file into the root directory
```
index.js
```

- Step-3: Install express dependencies  
```
npm install express
```

### Write this much in index.js
```
const express = require("express");

const app = express();
const PORT = process.env.PORT || 3000;

app.use(express.json());

// Basic routes
app.get("/", (req, res) => {
    // res.json({ message: 'Hello from Express' });
    res.send("Hey there!");
});

app.listen(PORT, () => {
    console.log(`Example app listening at port: ${PORT}`);
});

```

- Step-3: create a Dockerfile in the root directory
```
Dockerfile
```

### Write this much inside Dockerfile
```
FROM node:24-alpine

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

ENV PORT=3000

CMD ["node", "index.js"]

```

- Step-4: update the package.json or consult with developer
```
"scripts": {
    "start": "node index.js"
  },
```

- Step-5: create another file in the root directory
```
.dockerignore
```

### Update with this info
```
node_modules
npm-debug.log
```

## Execute the command on terminal
```
docker build -t express-app .
```
- t:type

## To run 
```
docker run -p 4000:3000 -e PORT=3000 --rm express-app
```
### or
## To run 
```
docker run -p 4000:3000 --env-file .env --rm express-app
```

## Open in browser
```
http://127.0.0.1:4000/
```
