FROM mhart/alpine-node:12 as build
WORKDIR /tmp/
COPY package.json package-lock.json ./
RUN npm ci --production

FROM node:12 as production
COPY --from=build /tmp/node_modules/ /app/node_modules/
WORKDIR /app

FROM mhart/alpine-node:12 as dev
WORKDIR /tmp/
COPY package.json package-lock.json ./
RUN npm install
