FROM node:16

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

EXPOSE 50053

CMD ["node", "audiovisualMicroservice.js"]
