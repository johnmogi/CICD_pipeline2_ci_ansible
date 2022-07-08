FROM node:14-alpine
RUN mkdir -p /home/app/node_modules && chown -R node:node /home/app

WORKDIR /home/app
COPY . /home/app

ENV port=8080
EXPOSE 8080

RUN npm install

RUN echo """
PORT=8080
HOST=0.0.0.0
NODE_ENV=development
HOST_URL=http://168.61.44.255:8080
COOKIE_ENCRYPT_PWD=superAwesomePasswordStringThatIsAtLeast32CharactersLong!

# Okta configuration
OKTA_ORG_URL=https://dev-96311573.okta.com
OKTA_CLIENT_ID=0oa57uv2e4ZbMvc8b5d7
OKTA_CLIENT_SECRET=-dS3ittft57jAzdyGrR1AmJhVD9qr2xapEJla7MF

# Postgres configuration
PGHOST=10.0.0.4
PGUSERNAME=postgres
PGDATABASE=postgres
PGPASSWORD=5pSi8DJ7yk8f
PGPORT=5432
""" > .env

RUN npm run initdb

#Start the app
CMD ["npm", "run","dev"] 

CMD npm run initdb && npm run dev