FROM node

WORKDIR /usr/scr/app

COPY package.json .

RUN npm install

COPY . .

EXPOSE 3000

CMD ["node", "index.js"]
