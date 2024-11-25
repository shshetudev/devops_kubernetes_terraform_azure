FROM node:8.16.1-alpine
WORKDIR /app
# We only need package.json, to be run first and if there is any change it will be on source code. That's why it's added up for optmization.
COPY package.json /app
RUN npm install
EXPOSE 5000

COPY . /app
CMD node index.js

#ENTRYPOINT ["node", "index.js"]
#COPY package.json /app
