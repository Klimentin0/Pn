FROM node:lts-alpine

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

# тестовый 
CMD ["npm", "run", "dev"]