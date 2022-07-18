FROM node:lts-alpine

EXPOSE 5000

ENV BACKEND_URL=http://localhost:8080

WORKDIR /usr/src/app

COPY . .

RUN npm install -g serve

RUN npm install && REACT_APP_BACKEND_URL=${BACKEND_URL} npm run build

CMD ["serve", "-s", "-l", "5000", "build"]
