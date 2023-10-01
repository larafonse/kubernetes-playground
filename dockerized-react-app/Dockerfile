FROM node:18-alpine

WORKDIR /dockerized-react-app/

COPY public/ /dockerized-react-app/public
COPY src/ /dockerized-react-app/src
COPY package.json /dockerized-react-app/


RUN npm install

CMD ["npm", "start"]
