```
# --- Stage-1 --- Build stage
FROM node:24-alpine AS builder

WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .

# --- Stage-2 --- Production stage
FROM node:24-alpine
WORKDIR /app
COPY --from=builder </from> </to>
EXPOSE 3000
ENV PORT=3000

CMD ["node", "server.js"]
```
