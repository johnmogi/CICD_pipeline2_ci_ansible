FROM node:14-alpine
RUN mkdir -p /home/app/node_modules && chown -R node:node /home/app

WORKDIR /home/app
COPY . /home/app

ENV port=8080
EXPOSE 8080

RUN npm install
# RUN npm run initdb

#Start the app
CMD ["npm", "run","dev"]