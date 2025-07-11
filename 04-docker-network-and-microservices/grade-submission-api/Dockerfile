## Base Image

## Working Directory

## Install Dependencies

## Copy Source code

## Expose container port

## Commands to execute application


FROM node:14

WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .

EXPOSE 3000

CMD ["node", "app.js"]

