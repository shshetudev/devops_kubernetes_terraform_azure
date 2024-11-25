FROM node:8.16.1-alpine
WORKDIR /app
# We only need package.json, to be run first and if there is any change it will be on source code. That's why it's added up for optmization.
COPY package.json /app
RUN npm install
EXPOSE 5000

COPY . /app
# Using CMD is very risky, because if we run with: `docker run -d -p 5001:5000 shshetudev/hello-world-nodejs:0.0.2.RELEASE ping google.com`, it will continuously ping google.com
# So the best approach is to use ENTRYPOINT, and overrirding ENTRYPOINT is a bit complex as well.
# CMD node index.js
ENTRYPOINT ["node", "index.js"]

#ENTRYPOINT ["node", "index.js"]
#COPY package.json /app
