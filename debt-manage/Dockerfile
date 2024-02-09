# Use official Node.js image as the base image
FROM node:latest

ADD package.json /tmp/package.json
RUN cd /tmp && npm install

# Copy deps
RUN mkdir -p /opt/nuxt-app && cp -a /tmp/node_modules /opt/debtmanage

# Setup workdir
WORKDIR /opt/nuxt-app
COPY . /opt/nuxt-app

# run
EXPOSE 3000
CMD ["npm", "start"]
