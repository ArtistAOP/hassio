# image for building
ARG BUILD_FROM
FROM $BUILD_FROM AS build-env

ENV LANG C.UTF-8

WORKDIR /app

RUN apk --no-cache update

RUN apk add --no-cache git
RUN git init
RUN git remote add origin https://github.com/Hypfer/Cybele.git
RUN git pull origin master

RUN apk add --no-cache npm
RUN apk add --no-cache python3
RUN apk add --no-cache g++
RUN npm install

RUN rm -r .git

# image for running
FROM $BUILD_FROM

ENV LANG C.UTF-8

WORKDIR /app

COPY --from=build-env /app .
RUN ln -s /config/cybele.json ./config.json

RUN apk --no-cache update
RUN apk add --no-cache nodejs

CMD node /app/app.js