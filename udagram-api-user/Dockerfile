FROM node:12
#Create app directory 
WORKDIR /usr/src/app
#Install app dependencies
#A wildcard is used to ensure both package.json and package-lock.json are copied where available 
COPY package*.json ./
RUN npm ci
#bundle app source

COPY . .
EXPOSE 8080
CMD ["npm", "run", "dev"]