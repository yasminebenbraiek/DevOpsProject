FROM node:16

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

EXPOSE 50052

CMD ["node", "magazineMicroservice.js"]
