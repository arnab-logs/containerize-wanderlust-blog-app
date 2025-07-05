#Stage 1
FROM node:21 AS backend-builder

#Setup working directory
WORKDIR /app

#Copy code
COPY . .

#Install dependencies
RUN npm i

#Stage 2
FROM node:21-slim

WORKDIR /app

#Copy Stage 1 as compressed
COPY --from=backend-builder /app .

COPY .env.sample .env

EXPOSE 5000

CMD ["npm", "start"]