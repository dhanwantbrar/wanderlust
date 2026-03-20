# stage 1
FROM node:20 AS frontend-builder

# Set working Dir 
WORKDIR /app

# copy the packeage.json and all
COPY package*.json ./

# skip 
ENV NPM_CONFIG_IGNORE_SCRIPTS=true

# install dependencies
RUN npm i

# copy the all code
COPY . .



# stage 2
FROM node:20-slim

# set working dir
WORKDIR /app

# set up dependencies
COPY --from=frontend-builder /app .

# copy the .env to .env.local
COPY .env.sample .env.local

# port
EXPOSE 5173

# app
CMD ["npm", "run", "dev", "--", "--host"]

