FROM mhart/alpine-node:12 as productiondependencies

# install dependencies
WORKDIR /app
COPY package.json package-lock.json ./
RUN npm install

FROM mhart/alpine-node:12
WORKDIR /app
COPY --from=productiondependencies /app .
COPY . .

EXPOSE 5000
RUN npm run dev
