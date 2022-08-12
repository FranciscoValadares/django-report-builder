#FROM node:lts
FROM node:10.13-alpine

EXPOSE 4200

RUN mkdir /home/node/app && chown node:node /home/node/app
RUN mkdir /home/node/app/node_modules && chown node:node /home/node/app/node_modules
RUN chown -R node:node  /home/node/app
RUN chmod 755  /home/node/app

WORKDIR  /home/node/app

USER node

COPY --chown=node:node package.json  ./

#RUN export NODE_OPTIONS=--openssl-legacy-provider
RUN npm install -f
#RUN npm ci --quiet
#RUN yarn install

COPY --chown=node:node . /home/node/app/
