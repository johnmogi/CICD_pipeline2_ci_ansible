FROM node:14-alpine
RUN mkdir -p /home/app/node_modules && chown -R node:node /home/app

WORKDIR /home/app
COPY . /home/app

ENV port=8080
EXPOSE 8080

RUN echo -e "\
    PORT=8080 n\
    HOST=0.0.0.0 n\
    NODE_ENV=development n\
    HOST_URL=http://168.61.44.255:8080 n\
    COOKIE_ENCRYPT_PWD=superAwesomePasswordStringThatIsAtLeast32CharactersLong! n\
    OKTA_ORG_URL=https://dev-96311573.okta.com n\
    OKTA_CLIENT_ID=0oa57uv2e4ZbMvc8b5d7 n\
    OKTA_CLIENT_SECRET=-dS3ittft57jAzdyGrR1AmJhVD9qr2xapEJla7MF n\
    PGHOST=10.0.0.4 n\
    PGUSERNAME=postgres n\
    PGDATABASE=postgres n\
    PGPASSWORD=5pSi8DJ7yk8f n\
    PGPORT=5432 n\
    " > .env

COPY package*.json ./

RUN npm install

CMD [ "npm", "run", "initdb" ]

ENTRYPOINT [ "npm", "run", "dev" ]