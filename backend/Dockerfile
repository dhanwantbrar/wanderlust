# stage 1
FROM node:20 AS backend-builder

# setup working dir
WORKDIR /app

# code
COPY . .

RUN npm i
# run tests

RUN npm run test

# stage 2
FROM node:20-slim

# setup the workin dir
WORKDIR /app

# copy the above stage as compressed
COPY --from=backend-builder /app .
 
COPY .env.sample .env

# ports
EXPOSE 8080

# app
CMD ["npm", "start"]


