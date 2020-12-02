# Create an image for the weather-app

FROM node

LABEL org.label-schema.version=v1.1

ENV NODE_ENV="production"

ENV PORT 3001

RUN mkdir -p /var/node

ADD src/ /var/node/

WORKDIR /var/node

RUN npm install

EXPOSE $PORT

ENTRYPOINT ./bin/www
