FROM node:19-alpine

LABEL maintainer="soumitra"

WORKDIR /home/soumitra/app

# Copy package.json directly from the build context root into the container's working directory
COPY package.json .

RUN npm install

# Copy the source code from the build context into the container
COPY src/ ./src

CMD ["node", "./src/server.js"]
