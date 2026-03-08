FROM node:20

WORKDIR /app

COPY package*.json ./


ENV NPM_CONFIG_IGNORE_SCRIPTS=true

RUN npm i

COPY . .

COPY .env.sample .env.local

EXPOSE 5173

CMD ["npm", "run", "dev", "--", "--host"]

