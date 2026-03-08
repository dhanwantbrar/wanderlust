FROM node:20

WORKDIR /app

COPY . .

RUN npm i

COPY .env.sample .env

EXPOSE 8080

CMD ["npm", "start"]


