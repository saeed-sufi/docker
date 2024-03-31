FROM node:20.11.1-alpine3.18

USER node 

WORKDIR /home/node/app 

COPY --chown=node:node package*.json .

RUN npm ci 

COPY --chown=node:node . .

CMD [ "node", "index.js" ]