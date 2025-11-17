```
docker compose
```

## Create some files in VS-Code
- Step-1
```
mkdir backend frontend
touch docker-compose.yml
```
# For Backend
- Step-2
```
cd backend
npm init -y
touch index.js Dockerfile .dockerignore
```

- Step-3
```
npm i express pg
```
- pg: postgresql

- Step-4: Modify package.json
```
"scripts": {
    "start": "node index.js"
  },
```

- Step-5: Paste insde index.js
```
const express = require("express");
const { Pool } = require("pg");

const app = express();
const PORT = process.env.PORT || 5000;

// Database connection

const pool = new Pool({
    user: process.env.DB_USER || "postgres",
    host: process.env.DB_HOST || "database",
    database: process.env.DB_NAME || "postgres",
    password: process.env.DB_PASS || "password",
    port: 5432,
});

app.get("/", (req, res) => {
    res.send("Hey there!, We are doing Docker-Compose");
});

app.get("/db", async (req, res) => {
    try {
        const result = await pool.query("SELECT NOW()");
        res.json({ time: result.rows[0] });
    } catch (error) {
        res.status(500).send(error.message);
    }
});

app.listen(PORT, () => {
    console.log(`Backend running on port: ${PORT}`);
});

```

- Step-6: Paste insde backend's Dockerfile
```
FROM node:24-alpine

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

EXPOSE 5000

CMD ["npm", "start"]
```

# For Frontend
- Step-1
```
touch Dockerfile .dockerignore
npm create vite@latest .
```

- Step-2: Paste inside frontend's Dockerfile
```
# --- Stage-1 --- Build stage
FROM node:24-alpine AS builder

WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build


# --- Stage-2 --- Serve stage
FROM nginx:alpine
WORKDIR /app
COPY --from=builder /app/dist /usr/share/nginx/html
EXPOSE 80
ENV PORT=3000

CMD ["nginx", "-g", "daemon off;"]
```

- Step-3 Modify/Update vite.config.js with
```
export default defineConfig({
    server: {
        host: "0.0.0.0",
        port: 5173,
    },
    plugins: [react()],
});
```

# For docker-compose.yml
```
version: "3.8"
services:
  frontend:
    build: ./frontend
    ports:
      - "3000:80"
    depends_on:
      - backend
      - database
    networks:
      - my-custom-network

  backend:
    build: ./backend
    ports:
      - "5001:5000"
    environment:
      DB_HOST: database
      DB_USER: postgres
      DB_PASS: password
      DB_NAME: postgres
    depends_on:
      - database
    networks:
      - my-custom-network

  database:
    image: postgres:16-alpine
    restart: always
    environment:
      POSTGRES_USER: postgres
      POSTGRES_PASSWORD: password
      POSTGRES_DB: postgres
    volumes:
      - pgdata:/var/lib/postgresql/data
    networks:
      - my-custom-network

volumes:
  pgdata:

networks:
  my-custom-network:
    driver: bridge
```

# Run on terminal
```
docker compose up
```
