FROM node:lts-alpine

EXPOSE 5000

WORKDIR /usr/src/app

COPY . .

RUN npm install -g serve

RUN npm install && npm run build

CMD ["serve", "-s", "-l", "5000", "build"]
