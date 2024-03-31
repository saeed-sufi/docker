# build stage
FROM node:20.11.1 

WORKDIR /build

COPY package*.json .

RUN npm ci

COPY . .

# runtime stage
FROM alpine:3.19

RUN apk add --update nodejs 

RUN addgroup -S node && adduser -S node -G node

USER node

RUN mkdir /home/node/app 

WORKDIR /home/node/app 

COPY --from=0 --chown=node:node /build .

CMD [ "node", "index.js" ]