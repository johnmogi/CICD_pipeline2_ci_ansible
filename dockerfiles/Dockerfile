FROM node:14-alpine
RUN mkdir -p /home/app/node_modules && chown -R node:node /home/app

WORKDIR /home/app
COPY ./app /home/app
# COPY package*.json /home/app

ENV port=8080
EXPOSE 8080

# RUN mv env .env

RUN npm install

CMD [ "npm", "run", "initdb" ]

ENTRYPOINT [ "npm", "run", "dev" ]